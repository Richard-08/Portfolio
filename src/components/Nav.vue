<template>
  <nav class="nav">
    <div class="container">
      <MenuBurger @show-menu="showMenuList" />

      <ul class="nav__list" :class="{ show: isShow }">
        <NavItem
          v-for="(link, index) in links"
          v-bind:key="index"
          v-bind:link="link"
        />
      </ul>
    </div>
  </nav>
</template>

<script>
import NavItem from "./NavItem.vue";
import MenuBurger from "./MenuBurger.vue";

export default {
  props: ["links"],
  data() {
    return {
      isShow: false,
    };
  },
  components: {
    NavItem,
    MenuBurger,
  },
  methods: {
    showMenuList() {
      this.isShow = !this.isShow;
    },
  },
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.nav {
  padding: 20px 0;

  &__list {
    display: flex;
    align-items: center;

    @include media(650px) {
      background-color: rgba(44, 62, 80, 0.9);
      padding: 20px;
      position: absolute;
      width: 80%;
      left: 50%;
      translate: -50%;
      top: 30px;
      flex-direction: column;
      transform: translateY(-50%) translateX(-50%) scale(0);
      transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1);
      z-index: 9999;
    }
  }

  &__list.show {
    transform: translateY(0) translateX(0) scale(1);
  }
}

/* .nav.footer .nav__list {
  display: flex;
  align-items: center;
  justify-content: end;

  @include media(570px) {
    flex-direction: column;
    justify-content: center;
  }
} */
</style>
