<template>
  <div id="app">
    <Header />
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
    <Footer />
  </div>
</template>

<script>
const INFO_BLOCKS = [
  {
    title: "NFT Swap",
    text:
      "We are building the underlying technology to support trusted NFT Swaps powered by Zora Score which will include Uniswap V3 LP tokens.",
    img: "/info_1.png",
    bgImg: "/stars_1.png",
    isReversed: false,
    animationDir: "lottie/1/data.json"
  },
  {
    title: "Algorithmic Credit",
    text:
      "We are building an algorithmic approach to credit. Our credit rating will determine creditworthiness and a API will be used in DeFi ecosystem.",
    img: "/info_2.png",
    isReversed: true,
    animationDir: "lottie/2/data.json"
  },
  {
    title: "Decentralized Governance",
    text:
      "Our developers just write code. Anyone can contribute to the project or join the growing community. Nobody is in charge.",
    img: "/info_3.png",
    bgImg: "/stars_2.png",
    isReversed: false,
    animationDir: "lottie/3/data.json"
  }
];
import Header from "@/components/Header.vue";
import Main from "@/components/Main.vue";
import Info from "@/components/Info.vue";
import Footer from "@/components/Footer.vue";
export default {
  name: "App",
  components: {
    Header,
    Main,
    Info,
    Footer
  },
  data() {
    return {
      info: INFO_BLOCKS
    };
  }
};
</script>

<style lang="scss">
@import "@/assets/scss/variables.scss";
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
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
