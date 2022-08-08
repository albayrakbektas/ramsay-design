<template>
  <div class="first-section">
    <div class="content">
      <h1 class="purple">Howdy,</h1>
      <h1>I'm</h1>
      <h1>Ramsay</h1>
    </div>
    <div class="resume">
      <div class="play-circle">
        <span class="material-symbols-outlined"> play_arrow </span>
      </div>
      <span class="watch-resume">Watch Resume</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "FirstSection",
};
</script>

<style lang="scss" scoped>
.content {
  display: grid;
  grid-template-columns: auto auto;
  grid-column-gap: 0.2rem;
  justify-content: start;
  margin-top: 5rem;
}
h1 {
  font-size: 6.54rem;
  line-height: 0;
  font-family: Montserrat, sans-serif;
}
.material-symbols-outlined {
  font-variation-settings: "FILL" 1, "wght" 400, "GRAD" 0, "opsz" 48;
}
.resume {
  display: grid;
  grid-template-columns: auto 1fr;
  grid-column-gap: 1rem;
  align-items: center;
  cursor: pointer;
  height: min-content;
  width: min-content;
  margin-top: 5rem;
  &:hover {
    .material-symbols-outlined,
    .watch-resume {
      color: #c32865;
    }
    .play-circle {
      border-color: #c32865;
    }
  }
}
.watch-resume {
  width: auto;
  font-size: 1.25rem;
  white-space: nowrap;
}
.resume:hover {
  color: #c32865;
}
.play-circle {
  height: 65px;
  width: 65px;
  border: 1px solid #ffffff;
  border-radius: 50%;
  display: grid;
  align-items: center;
  justify-content: center;
}
</style>
