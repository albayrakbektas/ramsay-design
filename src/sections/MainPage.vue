<template>
  <div>
    <div class="sections" @scroll="handleScroll">
      <FirstSection class="section" />
      <SecondSection id="second" class="section" />
      <ThirdSection class="section" />
      <FourthSection class="section" />
      <FifthSection class="section" />
      <SixthSection class="section" />
      <SeventhSection class="section" />
      <ArticlesSection class="section" />
      <ContactSection class="section" />
    </div>
    <!--    <div class="dots">-->
    <!--      <span-->
    <!--        class="w3-badge demo w3-border w3-hover-white"-->
    <!--        @click="currentDiv(1)"-->
    <!--      ></span>-->
    <!--      <span-->
    <!--        class="w3-badge demo w3-border w3-hover-white"-->
    <!--        @click="currentDiv(2)"-->
    <!--      ></span>-->
    <!--      <span-->
    <!--        class="w3-badge demo w3-border w3-hover-white"-->
    <!--        @click="currentDiv(3)"-->
    <!--      ></span>-->
    <!--      <span-->
    <!--        class="w3-badge demo w3-border w3-hover-white"-->
    <!--        @click="currentDiv(4)"-->
    <!--      ></span>-->
    <!--      <span-->
    <!--        class="w3-badge demo w3-border w3-hover-white"-->
    <!--        @click="currentDiv(5)"-->
    <!--      ></span>-->
    <!--      <span-->
    <!--        class="w3-badge demo w3-border w3-hover-white"-->
    <!--        @click="currentDiv(6)"-->
    <!--      ></span>-->
    <!--      <span-->
    <!--        class="w3-badge demo w3-border w3-hover-white"-->
    <!--        @click="currentDiv(7)"-->
    <!--      ></span>-->
    <!--      <span-->
    <!--        class="w3-badge demo w3-border w3-hover-white"-->
    <!--        @click="currentDiv(8)"-->
    <!--      ></span>-->
    <!--      <span-->
    <!--        class="w3-badge demo w3-border w3-hover-white"-->
    <!--        @click="currentDiv(9)"-->
    <!--      ></span>-->
    <!--    </div>-->
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
      counter: 0,
    };
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  // mounted() {
  //   window.addEventListener("scroll", this.handleScroll);
  //   this.handleScroll();
  //   // this.showDivs(this.slideIndex);
  // },
  created() {
    window.addEventListener("scroll", this.handleScroll);
    this.handleScroll();
  },
  methods: {
    handleScroll() {
      document.addEventListener(
        "scroll",
        function (ev) {
          let sec = document.querySelectorAll(".section");
          console.log(
            Array.from(sec).filter(
              (el) => el.getBoundingClientRect().top - height === 100
            )
          );
          const height = window.innerHeight;
          Array.from(sec).filter((el) => {
            let offset = el.getBoundingClientRect().top - height;
            console.log(offset);
            if (offset > 10 && offset < 20) {
              console.log("niasd");
              el.scrollIntoView(true);
            }
          });
          // window.addEventListener("mousemove", function (e) {
          //   console.log(e.clientX);
          // });
          // console.log(height, top);
          // if (offset <= 100) {
          //   sec.scrollIntoView(true);
          // }
          if (ev.target.scrollTop > 50) {
            console.log("");
          }
        },
        true
      );
    },
    // plusDivs(n) {
    //   this.showDivs((this.slideIndex += n));
    // },
    // currentDiv(n) {
    //   this.showDivs((this.slideIndex = n));
    // },
    // showDivs(n) {
    //   let i;
    //   let x = document.getElementsByClassName("section");
    //   let dots = document.getElementsByClassName("demo");
    //   if (n > x.length) {
    //     this.slideIndex = 1;
    //   }
    //   if (n < 1) {
    //     this.slideIndex = x.length;
    //   }
    //   for (i = 0; i < x.length; i++) {
    //     x[i].style.display = "none";
    //   }
    //   for (i = 0; i < dots.length; i++) {
    //     dots[i].className = dots[i].className.replace(" active-section", "");
    //   }
    //   x[this.slideIndex - 1].style.display = "grid";
    //   dots[this.slideIndex - 1].className += " active-section";
    // },
  },
};
</script>

<style lang="scss" scoped>
.sections {
  padding: 0 8rem;
  overflow-y: scroll;
}
.sections::-webkit-scrollbar {
  display: none;
}
.section {
  position: relative;
  height: 100vh;
  z-index: 98;
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
.active-section {
  //color: #c32865;
  //background: #c32865;
  //height: 13px;
  //width: 13px;
  z-index: 99;
}
</style>
