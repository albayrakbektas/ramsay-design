<template>
  <div class="fourth-right-container">
    <h1>The best websites</h1>
    <p>
      From tree make green multiply, great greater is. Fruit fowl blessed. Unto
      of man greater spirit you’ll beginning.
    </p>
    <RangeBar />
  </div>
</template>

<script>
import RangeBar from "@/components/RangeBar";
export default {
  name: "BestWebSites",
  components: { RangeBar },
};
</script>

<style scoped>
.fourth-right-container {
  display: grid;
  align-content: space-between;
}
</style>
