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
    transform: scale(0);

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

  @for $i from 1 through 14 {
    &__item:nth-child(#{$i}) {
      transition: all 0.8s ease (0.2s * $i);
    }
  }

  &__logo {
  }
}

.skills.active {
  @for $i from 1 through 14 {
    .skills__item:nth-child(#{$i}) {
      transform: scale(1);
    }
  }
}
</style>
