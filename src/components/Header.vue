<template>
  <header class="header diagonal-box" id="About Me">
    <div class="container">
      <div class="header__content diagonal-content">
        <h1 class="header__title">Hey, I am Bulat Ahtyamov</h1>
        <p class="header__text">
          I am a beginner <span>front-end developer</span>. This work inspires
          me and makes me happy. I want to continue to learn and develop in
          order to be the best. And the main thing to remember,
          <span>don`t panic!</span>
        </p>
      </div>
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style lang="scss">
.header {
  &__content {
    text-align: center;
  }

  &__title {
    text-transform: uppercase;
    margin-bottom: 25px;

    animation: leftAppear 1s linear;

    @keyframes leftAppear {
      0% {
        transform: translateX(-100%);
      }

      100% {
        transform: translateX(0);
      }
    }
  }

  &__text {
    background-color: #2c3e50;
    color: #fff;
    text-transform: uppercase;
    padding: 10px;
    animation: rightAppear 1s linear;

    @keyframes rightAppear {
      0% {
        transform: translateX(100%);
      }

      100% {
        transform: translateX(0);
      }
    }

    span {
      color: #41b883;
      font-weight: 900;
    }
  }
}
</style>
