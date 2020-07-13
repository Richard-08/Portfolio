<template>
  <li class="list-item">
    <a :href="`#${link}`" class="list-link">{{ link }}</a>
  </li>
</template>

<script>
export default {
  props: ["link"],
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.list-item {
  margin-right: 40px;
  animation: upAppear 1s cubic-bezier(0.175, 0.885, 0.32, 1.275);

  @keyframes upAppear {
    0% {
      transform: translateY(-100%);
    }
    100% {
      transform: translateY(0);
    }
  }
}

.list-item:last-child {
  margin-right: 0;
}

.list-link {
  display: block;
  padding: 20px 0;
  font-size: 18px;
  font-weight: 700;
  text-transform: uppercase;
  position: relative;
  overflow: hidden;
  transition: all 0.5s ease;

  @include media(650px) {
    color: #fff;
  }
}

.list-link::after,
.list-link::before {
  content: "";
  position: absolute;
  left: 0;
  width: 100%;
  height: 3px;
  background-color: #41b883;
  transition: all 0.5s ease;
}

.list-link::after {
  bottom: 0;
  transform: translateY(5px);
}

.list-link::before {
  top: 0;
  transform: translateY(100px);
}

.list-link:hover::after,
.list-link:hover::before {
  transform: translateY(0);
}

.list-link:hover {
  color: #41b883;
}

.footer {
  .list-link {
    color: $mainFontColor;
  }

  .list-item {
    @include media(570px) {
      margin-right: 0;
    }
  }
}

.nav {
  .list-item {
    @include media(650px) {
      margin-right: 0;
    }
  }
}
</style>
