<template>
  <agile :options="myOptions">
    <div class="slide" v-for="(project, index) in projects" v-bind:key="index">
      <img
        :src="require(`../assets/img/${project.name}.jpg`)"
        :alt="project.name"
      />

      <div class="slide__info">
        <h3>{{ project.name }}</h3>
        <a :href="project.link" class="slide__link" target="_blank"
          >Visit Website</a
        >
      </div>
    </div>

    <template slot="prevButton"><img :src="PrevIcon" alt="prev"/></template>
    <template slot="nextButton"><img :src="NextIcon" alt="next"/></template>
  </agile>
</template>

<script>
import { VueAgile } from "vue-agile";
import NextIcon from "../assets/img/next.svg";
import PrevIcon from "../assets/img/prev.svg";

export default {
  data() {
    return {
      projects: [
        {
          name: "Url shortening api",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Url-shortening-api-master/",
        },
        {
          name: "Manage landing page",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Manage-landing-page-master/",
        },
        {
          name: "Bookmark landing page",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Bookmark-landing-page-master/",
        },
        {
          name: "Rest countries api",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Rest-countries-api-with-color-theme-switcher-master/",
        },
        {
          name: "Easybank landing page",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Easybank-landing-page-master/",
        },
        {
          name: "Rock-paper-scissors game",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Rock-paper-scissors-master/",
        },
        {
          name: "Static job listing app",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Static-job-listings-master/",
        },
        {
          name: "Writing screen app",
          link:
            "https://richard-08.github.io/Daily-UI-Challenge/Writing%20screen/dist/",
        },
        {
          name: "Insure landing page",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Insure-landing-page-master/",
        },
        {
          name: "Clipboard landing page",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Сlipboard-landing-page-master/",
        },
        {
          name: "Fylo dark theme landing page",
          link:
            "https://richard-08.github.io/Frontend-Mentor-Challenges/Fylo-dark-theme-landing-page-master/",
        },
      ],
      NextIcon,
      PrevIcon,
      myOptions: {
        speed: 500,
        autoplay: true,
        timing: "ease-in-out",
      },
    };
  },
  components: {
    agile: VueAgile,
  },
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.agile {
  width: 80%;
  margin: 0 auto;
  @include animation(translateX(150%), 0.8s, ease, 0.8s);

  @include media(768px) {
    width: 100%;
  }

  &__actions {
    margin-top: 20px;
  }

  &__nav-button {
    background: transparent;
    border: none;
    color: #ccc;
    cursor: pointer;
    font-size: 24px;
    -webkit-transition-duration: 0.3s;
    transition-duration: 0.3s;
  }

  img {
    width: 20px;
  }

  &__nav-button:hover {
    color: #41b883;
  }

  &__dot {
    margin: 0 10px;

    @include media(570px) {
      margin: 0 8px;
    }
  }

  &__dot button {
    background-color: #d6d6d6;
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: block;
    height: 10px;
    font-size: 0;
    line-height: 0;
    margin: 0;
    padding: 0;
    -webkit-transition-duration: 0.3s;
    transition-duration: 0.3s;
    width: 10px;
  }
  &__dot--current button,
  &__dot:hover button {
    background-color: #41b883;
  }
}

.slide {
  background-color: mediumaquamarine;
  -webkit-box-align: center;
  align-items: center;
  color: #fff;
  display: -webkit-box;
  display: flex;
  height: 500px;
  -webkit-box-pack: center;
  justify-content: center;
  user-select: none;
  position: relative;
  overflow: hidden;
  cursor: grab;

  &__info {
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: rgba($color: #000000, $alpha: 0.5);

    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    opacity: 0;
    pointer-events: none;
    transition: all 0.3s ease;

    @include media(800px) {
      bottom: 0;
      height: 25%;
      opacity: 1;
      pointer-events: all;
    }

    h3 {
      color: #fff;
      margin-bottom: 20px;

      @include media(800px) {
        margin-bottom: 5px;
      }
    }
  }

  &:hover &__info {
    opacity: 1;
    pointer-events: all;
  }

  &:hover img {
    transform: scale(1.02);
  }

  &__link {
    padding: 10px;
    border: 2px solid #fff;
    border-radius: 20px;
    font-weight: 700;
    color: #fff;
    transition: all 0.3s ease;
  }

  &__link:hover {
    background-color: #fff;
    color: #41b883;
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: all 0.3s ease;
  }

  h3 {
    font-size: 32px;
    font-weight: 300;

    @include media(800px) {
      font-size: 24px;
    }
  }
}

.portfolio.active .agile {
  transform: translateX(0);
}
</style>
