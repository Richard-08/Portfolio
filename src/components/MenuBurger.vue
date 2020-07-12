<template>
  <div class="nav__burger" :class="{ active: isShow }" @click="showMenu">
    <span class="burger-toggle"></span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
    };
  },
  methods: {
    showMenu() {
      this.isShow = !this.isShow;
      this.$emit("show-menu");
    },
  },
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.nav {
  &__burger {
    display: none;
  }

  &__burger {
    @include media(650px) {
      display: block;
      position: relative;
      width: 25px;
      height: 20px;
      cursor: pointer;
    }

    .burger-toggle {
      background-color: $mainFontColor;
      position: absolute;
      width: 100%;
      height: 3px;
      left: 0;
      top: 9px;
      transition: all 0.3s ease 0s;
    }
  }

  &__burger:hover .burger-toggle {
    background-color: $secondary;
  }

  &__burger::before,
  &__burger::after {
    content: "";
    background-color: $mainFontColor;
    position: absolute;
    width: 100%;
    height: 3px;
    left: 0;
    transition: all 0.3s ease 0s;
  }

  &__burger:hover::before,
  &__burger:hover::after {
    background-color: $secondary;
  }

  &__burger::before {
    top: 0;
  }
  &__burger::after {
    bottom: 0;
  }

  &__burger.active::before {
    transform: rotate(45deg);
    top: 8.5px;
  }

  &__burger.active::after {
    transform: rotate(-45deg);
    bottom: 8.5px;
  }

  &__burger.active .burger-toggle {
    transform: scale(0);
  }
}
</style>
