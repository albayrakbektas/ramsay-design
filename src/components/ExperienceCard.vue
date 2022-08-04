<template>
  <div class="experience-card">
    <span class="experience-year">4</span>
    <div class="content">
      <span>Years</span>
      <span>Experience</span>
      <span>Working</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "ExperienceCard",
};
</script>

<style lang="scss" scoped>
.experience-card {
  border: 1px solid #ffffff;
  display: grid;
  align-items: center;
  padding: 5rem 2rem;
  .experience-year {
    font-size: 200px;
    text-align: center;
    font-family: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono",
      "Courier New", monospace;
  }
}
.content {
  display: grid;
  grid-template-columns: 1fr;
  text-align: end;
  padding-right: 4rem;
  span {
    font-size: 1.5rem;
  }
}
</style>
