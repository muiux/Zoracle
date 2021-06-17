<template>
  <div id="app">
    <Main />
    <Info
      v-for="(item, index) in info"
      :key="index"
      :title="item.title"
      :text="item.text"
      :img="item.img"
      :bg-img="item.bgImg"
      :isReversed="item.isReversed"
      :animationDir="item.animationDir"
      :class="`block-${index}`"
    />
    <TimeLine />
  </div>
</template>

<script>
const INFO_BLOCKS = [
  {
    title: "Zet Swap",
    text:
      "We are building the underlying technology to support trusted decentralized ERC20/NFT Swaps.",
    img: "/info_1.png",
    bgImg: "/stars_1.png",
    isReversed: false,
    animationDir: "lottie/1/data.json",
  },
  {
    title: "Zet Betting",
    text:
      "We are building a world first Meme Betting platform. Anyone can participate in Zet Betting with $ZET and other $MEME tokens that we support.",
    img: "/info_2.png",
    isReversed: true,
    animationDir: "lottie/2/data.json",
  },
  {
    title: "Decentralized Governance",
    text:
      "Our developers just write code. Anyone can contribute to the project or join the growing community. Nobody is in charge.",
    img: "/info_3.png",
    bgImg: "/stars_2.png",
    isReversed: false,
    animationDir: "lottie/3/data.json",
  },
];
import Main from "@/components/Main.vue";
import Info from "@/components/Info.vue";
import TimeLine from "@/components/TimeLine.vue";
export default {
  name: "App",
  components: {
    Main,
    Info,
    TimeLine,
  },
  data() {
    return {
      info: INFO_BLOCKS,
    };
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/variables.scss";
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
  position: relative;
  width: 100%;
  overflow-x: hidden;
  max-width: 100vw;
}

body {
  overflow-x: hidden;
  width: 100vw;
  background-color: var(--dark);
}

.block-0 {
  padding-top: 40px;

  @media screen and (max-width: 767px) {
    padding-top: 100px;
  }
}

.block-2 {
  padding-bottom: 40px;

  @media screen and (max-width: 767px) {
    padding-bottom: 60px;
  }
}
</style>
