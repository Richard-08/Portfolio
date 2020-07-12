<template>
  <footer class="footer">
    <div class="container">
      <SocialLinksList />

      <ul class="footer__nav-list">
        <NavItem
          v-for="(link, index) in links"
          :key="index"
          v-bind:link="link"
        />
      </ul>
    </div>
  </footer>
</template>

<script>
import NavItem from "./NavItem.vue";
import SocialLinksList from "./SocialLinksList.vue";

export default {
  data() {
    return {};
  },
  props: ["links"],
  components: {
    NavItem,
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

  @include media(650px) {
    padding-top: 100px;
  }

  &__nav-list {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    padding: 20px 0;

    @include media(570px) {
      flex-direction: column;
      justify-content: center;
    }
  }
}
</style>
