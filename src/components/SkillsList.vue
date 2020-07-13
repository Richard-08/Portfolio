<template>
  <div class="skills diagonal-box bg-1">
    <div class="container">
      <h2 class="skills__title" id="Skills">Skills & Experience</h2>
      <p class="skills__text">
        The main area of my competence is front-end development.
      </p>
      <p class="skills__text">
        HTML, CSS, JavaScript, building small and medium web apps with
        Vue.js/Vanilla JS, experience with RESTful services and APIs, responsive
        and mobile design, problem solving skills.
      </p>

      <ul class="skills__list">
        <SkillsItem
          v-for="(skill, index) in skills"
          v-bind:key="index"
          v-bind:skill="skill"
        />
      </ul>
    </div>
  </div>
</template>

<script>
import SkillsItem from "./SkillsItem.vue";

export default {
  props: ["skills"],
  data() {
    return {};
  },
  components: {
    SkillsItem,
  },
  methods: {},
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.skills {
  @include animation(translateX(-100%) translateY(50%), 1s, ease, 0s);

  &__title {
    text-align: center;
    margin-bottom: 30px;
    color: #fff;

    @include animation(translateX(100%), 0.8s, ease, 1.2s);
  }

  &__text {
    text-align: center;
    margin-bottom: 20px;
    color: #fff;

    @include animation(translateX(-150%), 0.8s, ease, 1.4s);
  }

  &__list {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(50px, 1fr));
    align-items: center;
    grid-gap: 15px;
  }
}

.skills.active {
  transform: translateX(0);

  .skills__title {
    transform: translateX(0);
  }

  .skills__text {
    transform: translateX(0);
  }
}
</style>
