<template>
  <div id="app">
    <Nav v-bind:links="links" />

    <Header />

    <SkillsList v-bind:skills="skills" />

    <Portfolio />

    <CTA />

    <Footer v-bind:links="links" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Nav from "./components/Nav.vue";
import SkillsList from "./components/SkillsList.vue";
import Portfolio from "./components/Portfolio.vue";
import CTA from "./components/CTA.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  data() {
    return {
      links: ["About Me", "Skills", "Portfolio", "Contact Me"],
      skills: [
        { name: "Babel" },
        { name: "BEM" },
        { name: "Bootstrap" },
        { name: "CSS-3" },
        { name: "ES6" },
        { name: "Git" },
        { name: "HTML-5" },
        { name: "JavaScript" },
        { name: "NodeJS" },
        { name: "npm" },
        { name: "Pug" },
        { name: "Sass" },
        { name: "Vue" },
        { name: "Webpack" },
      ],
    };
  },
  components: {
    Header,
    Nav,
    SkillsList,
    Portfolio,
    CTA,
    Footer,
  },
};
</script>

<style lang="scss">
@import "./assets/scss/_stylebase.scss";

html {
  scroll-behavior: smooth;
}

body {
  background-color: $main-bg;
  font-family: $mainFont;
  color: $mainFontColor;
}

* {
  font-family: $mainFont;
  color: $mainFontColor;
}

input,
textarea,
button {
  font-family: $mainFont;
  font-size: 18px;
}

/* ----------------General styles--------------- */

img {
  max-width: 100%;
}

.container {
  max-width: 100%;
  width: 1160px;
  padding: 0 20px;
  margin: 0 auto;
  position: relative;
}

.diagonal-box {
  position: relative;
  padding: $skew-padding 0;

  &::before {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    transform: skewY($angle);
    transform-origin: 50% 0;
    outline: 1px solid transparent;
    backface-visibility: hidden;
  }
}

.bg-1::before {
  background-image: $bg;
}

.bg-3::before {
  background-image: $bg;
}

.diagonal-content {
  transform: skewY($angle);
}
</style>
