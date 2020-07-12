<template>
  <ul class="social-links">
    <SocialLinkItem v-for="(link, index) in links" :key="index" :link="link" />
  </ul>
</template>

<script>
import SocialLinkItem from "./SocialLinkItem.vue";

export default {
  data() {
    return {
      links: [
        {
          name: "github",
          link: "https://github.com/Richard-08",
          icon: "fab fa-github",
        },
        {
          name: "twitter",
          link: "https://twitter.com/AhtyamovBulat",
          icon: "fab fa-twitter",
        },
      ],
    };
  },
  components: {
    SocialLinkItem,
  },
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.social-links {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  position: relative;
  z-index: 10;
  margin-bottom: 20px;

  @include media (570px) {
    justify-content: center;
    margin-bottom: 0;
  }
}
</style>
