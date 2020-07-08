<template>
  <li class="skills__item" :data-title="skill.name">
    <img
      class="skills__logo"
      :src="require(`../assets/img/${skill.name.toLowerCase()}.svg`)"
      :alt="skill.name"
    />
  </li>
</template>

<script>
export default {
  props: ["skill"],
};
</script>

<style lang="scss">
.skills {
  &__item {
    position: relative;
    cursor: pointer;

    &::after {
      content: attr(data-title);
      position: absolute;
      bottom: -35px;
      left: 50%;
      padding: 5px;
      border-radius: 5px;
      color: #fff;
      background-color: rgba($color: #000000, $alpha: 0.3);
      transform: scaleY(0) translate(-50%);
      transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }

    &:hover::after {
      transform: scaleY(1) translate(-50%);
    }
  }

  &__logo {
  }
}
</style>
