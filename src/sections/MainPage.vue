<template>
  <div class="sections">
    <FirstSection class="section" />
    <SecondSection class="section" />
    <ThirdSection class="section" />
    <FourthSection class="section" />
    <FifthSection class="section" />
    <SixthSection class="section" />
    <SeventhSection class="section" />
    <ArticlesSection class="section" />
    <ContactSection class="section" />
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
      <span
        class="w3-badge demo w3-border w3-hover-white"
        @click="currentDiv(5)"
      ></span>
      <span
        class="w3-badge demo w3-border w3-hover-white"
        @click="currentDiv(6)"
      ></span>
      <span
        class="w3-badge demo w3-border w3-hover-white"
        @click="currentDiv(7)"
      ></span>
      <span
        class="w3-badge demo w3-border w3-hover-white"
        @click="currentDiv(8)"
      ></span>
      <span
        class="w3-badge demo w3-border w3-hover-white"
        @click="currentDiv(9)"
      ></span>
    </div>
  </div>
</template>

<script>
import FourthSection from "@/sections/AboutUsSection";
import FirstSection from "@/sections/MeSection";
import SecondSection from "@/sections/WhatIDoSection";
import ThirdSection from "@/sections/ResumeSection";
import FifthSection from "@/sections/MyWorksSection";
import SixthSection from "@/sections/PartnersSection";
import SeventhSection from "@/sections/ReviewsSection";
import ArticlesSection from "@/sections/ArticlesSection";
import ContactSection from "@/sections/ContactSection";
export default {
  name: "MainPage",
  components: {
    ContactSection,
    ArticlesSection,
    SeventhSection,
    SixthSection,
    FifthSection,
    ThirdSection,
    SecondSection,
    FirstSection,
    FourthSection,
  },
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
  display: grid;
  grid-template-rows: repeat(9, 1fr);
  justify-self: center;
  gap: 1rem;
  position: absolute;
  right: calc(5rem - (13px / 2));
  top: calc(50% - 6rem);
  z-index: 5;
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
