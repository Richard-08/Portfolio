<template>
  <li class="social-links__item">
    <a :href="link.link" target="_blank" class="social-links__link"
      ><i :class="link.icon"></i
    ></a>
  </li>
</template>

<script>
export default {
  props: ["link"],
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.social-links {
  &__item {
    margin-right: 30px;
  }

  &__item:last-child {
    margin-right: 0;
  }

  &__link {
    font-size: 35px;

    i {
      transition: all 0.3s ease;
    }
  }
  &__link:hover i {
    color: #41b883;
  }
}
</style>
