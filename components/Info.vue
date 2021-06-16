<template>
  <div class="info">
    <div class="bg" v-if="bgImg">
      <img :src="bgImg" alt="" class="bg__img" />
    </div>
    <div :class="['container', { reverse: isReversed }]">
      <div :class="['img__block', { moved: isReversed }]" ref="anim"></div>
      <div class="content__block">
        <h2 class="info__title">{{ title }}</h2>
        <p class="info__text">{{ text }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import lottie from "lottie-web/build/player/lottie";

export default {
  name: "Info",
  props: {
    title: String,
    text: String,
    img: String,
    bgImg: String,
    isReversed: Boolean,
    animationDir: String
  },
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
      path: this.animationDir
    });
  }
};
</script>

<style scoped lang="scss">
.info {
  width: 100%;
  position: relative;

  @media screen and (max-width: 767px) {
        margin-bottom: 40px;
      }

  .bg {
    position: absolute;
    z-index: 2;
    width: 100%;
    max-width: 1400px;
    left: 50%;
    top: 50%;
    transform: translateX(-50%) translateY(-50%);
    height: 100%;

    img {
      width: 100%;
    }
  }
}
.container {
  max-width: 906px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
  z-index: 3;

  &.reverse {
    flex-direction: row-reverse;
  }

  .img__block {
    max-width: 48%;

    &.moved {
      position: relative;
      top: -80px;

      @media screen and (max-width: 767px) {
        top: 0;
      }
    }

    img {
      width: 100%;
    }
  }

  .content__block {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    text-align: left;
    max-width: 370px;
    width: 41%;

    .info__title {
      margin-bottom: 32px;
      font-family: "Jockey";
      font-size: 54px;
      line-height: 0.8;
      letter-spacing: 0.01em;
      color: #ffffff;
    }

    .info__text {
      font-family: "RobotoCondensed";
      font-style: normal;
      font-weight: normal;
      font-size: 14px;
      line-height: 24px;
      letter-spacing: 0.01em;
      color: #ffffff;
    }
  }
}
@media screen and (max-width: 1200px) {
  .container {
    max-width: 1000px;
    justify-content: space-around;

    .content__block {
      padding: 0 20px;
      .info__title {
        font-size: 42px;
      }
      .info__text {
        font-size: 16px;
      }
    }
  }
}
@media screen and (max-width: 991.98px) {
  .container {
    .content__block {
      padding: 0 32px;
      .info__title {
        font-size: 36px;
      }
    }
  }
}

@media (max-width: 767.98px) {
  .container .img__block {
    max-width: 100%;
  }

  .container {
    .content__block {
      max-width: none;
      width: 100%;
      margin-top: 36px;
    }
  }
}

@media screen and (max-width: 576px) {
  .container {
    flex-direction: column;
    &.reverse {
      flex-direction: column;
    }
    .img__block {
      max-width: 240px;
    }

    .content__block {
      margin-bottom: 20px;

      .info__title {
        font-size: 54px;
        margin: 14px 0;
      }
    }
  }
}
</style>
