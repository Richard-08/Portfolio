<template>
  <nav class="nav" v-bind:class="{ footer: isFooter }">
    <div class="container">
      <ul class="nav__list">
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

export default {
  props: ["links", "isFooter"],
  components: {
    NavItem,
  },
};
</script>

<style lang="scss">
.nav {
  padding: 20px 0;

  &__list {
    display: flex;
    align-items: center;
  }
}

.nav.footer .nav__list {
   justify-content: end;
}
</style>
