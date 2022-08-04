<template>
  <div class="sections">
    <FirstSection class="section" />
    <SecondSection class="section" />
    <ThirdSection class="section" />
    <FourthSection class="section" />
    <div class="dots">
      <span
        class="w3-badge demo w3-border w3-hover-white"
        @click="currentDiv(1)"
      ></span>
      <span
        class="w3-badge demo w3-border w3-hover-white"
        @click="currentDiv(2)"
      ></span>
      <span
        class="w3-badge demo w3-border w3-hover-white"
        @click="currentDiv(3)"
      ></span>
      <span
        class="w3-badge demo w3-border w3-hover-white"
        @click="currentDiv(4)"
      ></span>
    </div>
  </div>
</template>

<script>
import FourthSection from "@/sections/FourthSection";
import FirstSection from "@/sections/FirstSection";
import SecondSection from "@/sections/SecondSection";
import ThirdSection from "@/sections/ThirdSection";
export default {
  name: "MainPage",
  components: { ThirdSection, SecondSection, FirstSection, FourthSection },
  data() {
    return {
      slideIndex: 1,
    };
  },
  mounted() {
    this.showDivs(this.slideIndex);
  },
  methods: {
    plusDivs(n) {
      this.showDivs((this.slideIndex += n));
    },
    currentDiv(n) {
      this.showDivs((this.slideIndex = n));
    },
    showDivs(n) {
      let i;
      let x = document.getElementsByClassName("section");
      let dots = document.getElementsByClassName("demo");
      if (n > x.length) {
        this.slideIndex = 1;
      }
      if (n < 1) {
        this.slideIndex = x.length;
      }
      for (i = 0; i < x.length; i++) {
        x[i].style.display = "none";
      }
      for (i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(" active", "");
      }
      x[this.slideIndex - 1].style.display = "grid";
      dots[this.slideIndex - 1].className += " active";
    },
  },
};
</script>

<style lang="scss" scoped>
.sections {
  padding: 0 8rem;
}
.section {
  display: none;
}
.w3-left,
.w3-right,
.w3-badge {
  cursor: pointer;
}
.w3-badge {
  height: 8px;
  width: 8px;
  padding: 0;
  margin: auto;
}
.dots {
  display: inline-flex;
  justify-self: center;
  column-gap: 1rem;
  position: absolute;
  right: calc(3rem - (13px / 2));
  top: 50%;
  z-index: 5;
  transform: rotate(90deg);
}
.w3-transparent {
  background-color: unset !important;
}
.active {
  color: #c32865;
  background: #c32865;
  height: 13px;
  width: 13px;
}
</style>
