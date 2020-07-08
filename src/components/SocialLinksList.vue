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
.social-links {
  display: flex;
  align-items: center;
  justify-content: end;
  position: relative;
  z-index: 10;
  margin-bottom: 20px;
}
</style>
