<template>
  <div class="project">
    <h4 class="project__title">{{ project.name }}</h4>
    <a :href="project.link" class="project__link" target="_blank">More Info</a>
  </div>
</template>

<script>
export default {
  props: ["project"],
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.project {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  padding: 10px;
  background-color: #ffffff;
  box-shadow: 0px 0px 10px 3px rgba($color: #000000, $alpha: 0.05);
  transition: all 0.3s ease;

  &:nth-child(1) {
    transform: translateY($skew-padding * 1.5);

    @include media(768px) {
      transform: translateY($skew-padding * 0.5);
    }
  }
  &:nth-child(2) {
    transform: translateY($skew-padding * 1);

    @include media(768px) {
      transform: translateY($skew-padding * 0);
    }
  }
  &:nth-child(3) {
    transform: translateY($skew-padding * 0.5);

    @include media(768px) {
      transform: translateY($skew-padding * 1);
    }
  }
  &:nth-child(4) {
    transform: translateY($skew-padding * 0);

    @include media(768px) {
      transform: translateY($skew-padding * 0.5);
    }
  }

  &__title {
    margin-bottom: 20px;
  }

  &__link {
    padding: 10px;
    font-weight: 700;
    color: #41b883;
    transition: all 0.3s ease;
    position: relative;
    z-index: 2;
  }

  &__link::after {
    content: "";
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 2px;
    background-color: #41b883;
    transition: all 0.3s ease;
    z-index: -1;
  }

  &__link:hover::after {
    height: 100%;
  }

  &__link:hover {
    color: #fff;
  }
}
</style>
