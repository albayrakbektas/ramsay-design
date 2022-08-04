<template>
  <div class="sections">
    <FourthSection />
  </div>
</template>

<script>
import FourthSection from "@/sections/FourthSection";
export default {
  name: "MainPage",
  components: { FourthSection },
};
</script>

<style lang="scss" scoped>
.sections {
  padding: 0 8rem;
}
</style>
