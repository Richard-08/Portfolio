<template>
  <div class="projects">
    <ProjectItem
      v-for="(project, index) in projects"
      v-bind:key="index"
      v-bind:project="project"
    />
  </div>
</template>

<script>
import ProjectItem from "./ProjectItem.vue";

export default {
  data() {
    return {
      projects: [
        {
          name: "CodeWars Kata Solutions",
          link: "https://github.com/Richard-08/CodeWars-Kata-Solutions",
        },
        {
          name: "App Ideas Collection Projects",
          link: "https://github.com/Richard-08/JS-Practice",
        },
        {
          name: "Daily UI Challenges",
          link: "https://github.com/Richard-08/Daily-UI-Challenge",
        },
        {
          name: "Frontend Mentor Challenges",
          link: "https://github.com/Richard-08/Frontend-Mentor-Challenges",
        },
      ],
    };
  },
  components: {
    ProjectItem,
  },
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.projects {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 30px;
  margin: 50px 0;

  @include media(768px) {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
