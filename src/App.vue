<template>
  <div id="app">
    <div class="header-position container">
      <AppHeader />
    </div>
    <!--    <div class="bg-img"></div>-->
    <MainPage />
    <div class="footer-position container">
      <AppFooter />
    </div>
  </div>
</template>

<script>
import MainPage from "@/sections/MainPage";
import AppHeader from "@/components/AppHeader";
import AppFooter from "@/components/AppFooter";
export default {
  name: "App",
  components: { AppFooter, AppHeader, MainPage },
};
</script>

<style lang="scss">
* {
  z-index: 1;
}
html {
  font-size: 12px;
  @media only screen and (min-width: 768px) {
    font-size: 13px;
  }
}
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  background-color: #1b1b1b;
  height: 100vh;
  max-height: 100vh;
  overflow: scroll;
}
body::-webkit-scrollbar {
  display: none;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
a {
  text-decoration: none;
  &:hover {
    text-decoration: underline;
    text-decoration-color: #ffffff;
  }
}
span,
p,
h1,
h2,
a {
  color: #ffffff;
}
.purple {
  color: #c32865;
}
.footer-position {
  padding-top: 0 !important;
}
.container {
  padding: 2rem 4rem;
}
.header-position {
  position: sticky;
  top: 0;
}
.footer-position {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
}
.bg-text {
  z-index: 1;
}
.rotate-text {
  position: absolute;
  top: 70px;
  left: 70px;
  bottom: 0;
  font-size: 11rem;
  font-weight: bold;
  transform-origin: 50% 50%;
  transform: rotate(-90deg);
  /* Safari */
  -webkit-transform: rotate(-90deg);
  /* Firefox */
  -moz-transform: rotate(-90deg);
  /* IE */
  -ms-transform: rotate(-90deg);
  /* Opera */
  -o-transform: rotate(-90deg);
  color: #757575;
  opacity: 0.1;
}
//.bg-img {
//  position: absolute;
//  z-index: 0;
//  top: 0;
//  bottom: 0;
//  left: 0;
//  right: 0;
//  height: 100%;
//  width: 100%;
//  background-repeat: no-repeat;
//  background-size: cover;
//  background-image: url("http://paul-themes.com/wordpress/ramsay/wp-content/uploads/2020/01/attachment-18.jpg");
//}
</style>
