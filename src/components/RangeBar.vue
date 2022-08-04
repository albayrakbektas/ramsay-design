<template>
  <div class="range-bar-container">
    <div class="range-bar-header">
      <div class="range-bar-title"></div>
      <div class="range-bar-percent"></div>
    </div>
    <div class="range-bar"></div>
  </div>
</template>

<script>
export default {
  name: "RangeBar",
};
</script>

<style lang="scss" scoped>
.range-bar-container {
  display: grid;
  grid-template-rows: 1fr 1fr;
  grid-gap: 1rem;
  align-items: center;
}
.range-bar-header {
  display: grid;
  grid-template-columns: auto auto;
  justify-content: space-between;
}
</style>
