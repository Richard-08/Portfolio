<template>
  <div class="cta diagonal-box bg-3">
    <div class="container diagonal-content">
      <h2 class="cta__title" id="Contact Me">Contact Me</h2>

      <form class="cta__form" @submit.prevent="onSubmit">
        <div class="cta__inputs">
          <input
            type="text"
            class="cta__input-name"
            placeholder="Your Name"
            v-model="name"
          />
          <input
            type="email"
            class="cta__input-email"
            placeholder="Email"
            v-model="email"
          />
        </div>

        <textarea
          rows="10"
          placeholder="Message"
          class="cta__message-textarea"
          v-model="text"
        ></textarea>

        <button type="submit" class="cta__submit-btn">Submit</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      email: "",
      text: "",
    };
  },
  methods: {
    onSubmit() {
      const feedback = {
        name: this.name,
        email: this.email,
        text: this.text,
      };

      fetch("https://portfolio-app-abda8.firebaseio.com/feedback.json", {
        method: "POST",
        body: JSON.stringify(feedback),
        headers: {
          "Content-Type": "application/json",
        },
      });

      this.name = "";
      this.email = "";
      this.text = "";
    },
  },
};
</script>

<style lang="scss">
@import "../assets/scss/_stylebase.scss";

.cta {
  @include animation(translateX(100%) translateY(-50%), 0.8s, ease, 0s);

  &__title {
    text-align: center;
    color: #fff;
    @include animation(translateX(-100%), 0.8s, ease, 1s);
  }

  &__form {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 40px 30px;

    @include animation(translateX(150%), 0.8s, ease, 1.5s);
  }

  &__inputs {
    width: 100%;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 25px;

    @include media(650px) {
      grid-template-columns: 1fr;
    }
  }

  &__input-name {
  }

  &__input-email {
  }

  &__input-name,
  &__input-email,
  &__message-textarea {
    padding: 10px;
    transition: all 0.3s ease;
    background-color: rgba(0, 0, 0, 0.3);
    font-weight: 700;
    color: #fff;
    transition: all 0.3s ease;
  }

  &__input-name:focus,
  &__input-email:focus,
  &__message-textarea:focus {
    background-color: #fff;
    color: #2c3e50;
    transform: translateY(-3px) translateX(-3px);
    box-shadow: 7px 7px 0px 3px rgba(0, 0, 0, 0.3);
  }

  &__message-textarea {
    width: 100%;
    margin: 25px 0;
  }

  &__submit-btn {
    max-width: 100%;
    width: 300px;
    padding: 10px;
    text-transform: uppercase;
    font-weight: 700;
    cursor: pointer;
    background-color: #41b883;
    color: #fff;
    transition: all 0.3s cubic-bezier(0.075, 0.82, 0.165, 1);

    &:hover {
      transform: translateY(-3px) translateX(-3px);
      box-shadow: 7px 7px 0px 3px rgba(65, 184, 131, 0.5);
    }

    &:active {
      transform: translateY(0) translateX(0);
      box-shadow: none;
    }
  }
}

.cta.active {
  transform: translateX(0);
  .cta__title {
    transform: translateX(0);
  }

  .cta__form {
    transform: translateX(0);
  }
}
</style>
