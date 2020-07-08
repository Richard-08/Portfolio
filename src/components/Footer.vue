<template>
  <footer class="footer">
    <div class="container">
      <SocialLinksList />
      <Nav v-bind:links="links" v-bind:isFooter="isFooter" />
    </div>
  </footer>
</template>

<script>
import Nav from "./Nav.vue";
import SocialLinksList from "./SocialLinksList.vue";

export default {
  data() {
    return {
      isFooter: true,
    };
  },
  props: ["links"],
  components: {
    Nav,
    SocialLinksList,
  },
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.footer {
  position: relative;
  margin-top: $clip-padding * -1;
  padding-top: 130px;
  clip-path: polygon(0% $clip-padding * 2, 100% 0%, 100% 100%, 0% 100%);
}
</style>
