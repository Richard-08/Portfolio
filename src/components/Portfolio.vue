<template>
  <div class="portfolio diagonal-box bg-2">
    <div class="container">
      <h2 class="portfolio__title" id="Portfolio">Projects</h2>

      <Slider />

      <h3 class="portfolio__subtitle">More code</h3>

      <Projects />
    </div>
  </div>
</template>

<script>
import Slider from "./Slider.vue";
import Projects from "./Projects.vue";

export default {
  components: {
    Slider,
    Projects,
  },
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.portfolio {
  text-align: center;
  &__title,
  &__subtitle {
    margin-bottom: 30px;
    @include animation(translateX(-100%), 0.8s, ease, 0s);
  }

  &__subtitle {
    margin-top: 30px;
    @include animation(translateX(-100%), 0.8s, ease, 1s);
  }
}

.portfolio.active {
  .portfolio__title,
  .portfolio__subtitle {
    transform: translateX(0);
  }
}
</style>
