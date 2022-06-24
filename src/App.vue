<template>
  <h1>Catch me if u can</h1>
  <button @Click="start" :disabled="startClick">Play</button>
  <div v-if="startClick">
    <Click :delay="delay" @endGame="endGame" />
  </div>
  <div v-if="end">
    <Result :score="score" />
  </div>
</template>
 
<script>
import Click from "./components/Block.vue";
import Result from "./components/Result.vue";
export default {
  name: "App",
  components: {
    Click,
    Result,
  },
  data() {
    return {
      startClick: false,
      delay: null,
      score: 0,
      end: false,
    };
  },
  methods: {
    start() {
      this.startClick = true;
      this.delay = 2000 + Math.random() * 5000;
    },
    endGame(score) {
      this.score = score;
      this.startClick = false;
      this.end = true;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
