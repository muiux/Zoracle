<template>
  <div class="main">
    <div class="content">
      <h1 class="main__title">
        DEFI <span class="brand">O</span>RACLE PLATFORM
      </h1>
      <p class="main__text">
        Amet minim mollit non deserunt ullamco est sit aliqua dolor do amet
        sint. Velit officia consequat duis enim velit mollit. Exercitation
        veniam consequat sunt nostrud amet.
      </p>
      <a href="google.com" class="main__btn">see swaps</a>
    </div>
    <div class="bg" ref="anim">
    </div>
    <button @click="refresh">Click Me!</button>
  </div>
</template>

<script>
import lottie from "lottie-web/build/player/lottie";
export default {
  name: "Main",
  data() {
    return {
      animationNode: null
    };
  },
  mounted() {
    this.animationNode = this.$refs.anim;

    lottie.loadAnimation({
      container: this.animationNode,
      renderer: "svg",
      loop: true,
      autoplay: true,
      path: "lottie/main/data.json"
    });
  },
  methods: {
    refresh: function(event) {
      alert('Hi');
    }
  }
};
</script>

<style scoped lang="scss">
.main {
  width: 100%;
  position: relative;

  .content {
    position: absolute;
    top: 185px;
    left: 182px;
    text-align: left;
    max-width: 525px;
    z-index: 199;
  }

  .main__title {
    margin-bottom: 32px;
    font-family: "Jockey";
    font-style: normal;
    font-weight: normal;
    font-size: 106px;
    line-height: 88.5%;

    color: #f8f8f8;
  }

  .main__text {
    margin-bottom: 30px;
    font-family: "RobotoCondensed";
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 24px;
    letter-spacing: 0.01em;
    color: #f8f8f8;
  }

  .main__btn {
    padding: 16px 60px;
    font-family: "Lato";
    font-weight: 600;
    font-size: 18px;
    line-height: 1.14;
    text-transform: capitalize;
    color: #ffffff;
    background-color: var(--brand);
    cursor: pointer;
    border-radius: 8px;
    transition: 0.25 box-shadow ease-out;

    &:hover {
      box-shadow: 0px 2px 4px 3px #cf2f21;
    }
  }
}
.bg__img {
  width: 100%;
  // max-width: 1920px;
}

@media screen and (max-width: 1200px) {
  .main .main__title {
    margin-bottom: 24px;
    font-size: 48px;
  }
  .main .content {
    top: 180px;
    left: 90px;
  }
  .main .main__text {
    width: 400px;
    font-size: 16px;
  }
  .main .main__btn {
    font-size: 16px;
    padding: 14px 50px;
  }
}
@media screen and (max-width: 991.98px) {
  .main .main__title {
    margin-bottom: 24px;
    font-size: 36px;
  }
  .main .content {
    top: 120px;
    left: 60px;
  }
  .main .main__text {
    width: 330px;
  }
  .main .main__btn {
    font-size: 14px;
    padding: 12px 40px;
  }
}
@media screen and (max-width: 767.98px) {
  .main .main__title {
    margin-bottom: 24px;
    font-size: 36px;
  }
  .main .content {
    top: 120px;
    left: 60px;
  }
  .main .main__text {
    width: 300px;
  }
}
@media screen and (max-width: 576px) {
  .main .main__title {
    font-size: 20px;
    margin-bottom: 8px;
  }
  .main .content {
    top: 75px;
    left: 25px;
  }
  .main .main__text {
    font-size: 8px;
    width: 140px;
    margin-bottom: 8px;
    line-height: 1.8;
  }
  .main .main__btn {
    font-size: 10px;
    padding: 5px 20px;
  }
}
</style>
