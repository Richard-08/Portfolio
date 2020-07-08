<template>
  <li class="nav__list-item">
    <a :href="`#${link}`" class="nav__list-link">{{ link }}</a>
  </li>
</template>

<script>
export default {
  props: ["link"],
};
</script>

<style lang="scss">
.nav {
  &__list-item {
    margin-right: 40px;
  }

  &__list-item:last-child {
    margin-right: 0;
  }

  &__list-link {
    display: block;
    padding: 20px 0;
    font-size: 18px;
    font-weight: 700;
    text-transform: uppercase;
    position: relative;
    overflow: hidden;
    transition: all 0.5s ease;
  }

  &__list-link::after,
  &__list-link::before {
    content: "";
    position: absolute;
    left: 0;
    width: 100%;
    height: 3px;
    background-color: #41b883;
    transition: all 0.5s ease;
  }

  &__list-link::after {
    bottom: 0;
    transform: translateY(5px);
  }

  &__list-link::before {
    top: 0;
    transform: translateY(100px);
  }

  &__list-link:hover::after,
  &__list-link:hover::before {
    transform: translateY(0);
  }

  &__list-link:hover {
    color: #41b883;
  }
}

.nav.footer {
  &__list-link {
    
  }
}
</style>
