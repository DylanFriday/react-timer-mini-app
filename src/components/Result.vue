<template>
  <p>Result is {{ score }}ms</p>
  <div v-if="score < 250">
    <p>U are cheating xD</p>
  </div>
  <div v-else-if="score > 250 && score < 500">
    <p>Nice try(just a nirmal speed xD)</p>
  </div>
  <div v-else>
    <p>slow as fuck mofo noob</p>
  </div>
</template>

<script>
export default {
  props: ["score"],
};
</script>

<style>
</style>