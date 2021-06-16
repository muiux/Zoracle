<template>
  <header :class="['header', { scrolled: scrollPosition > 20 }]">
    <div class="container header__container">
      <div class="logo__container">
        <img src="@/assets/img/logo.png" alt="" class="logo" />
      </div>
      <div class="nav">
        <ul class="nav__container">
          <li v-for="(item, index) in NAV_LIST" :key="index" class="nav__item">
            <a :href="item.link" class="nav_link">{{ item.label }}</a>
          </li>
        </ul>
        <a href="https://twitter.com/z0racles" class="twitter_btn">
          <span class="btn__text">Our twitter</span>
          <img src="@/assets/img/twitter.svg" alt="" class="btn__logo" />
        </a>
      </div>
      <div class="burger" @click.stop="toggleMenu" v-if="!isMenuOpened">
        <img src="@/assets/img/hamburger.svg" alt="" />
      </div>
      <div
        :class="['mobile__nav', { active: isMenuOpened }]"
        v-click-outside="onClickOutside"
      >
        <div class="cross" @click.stop="toggleMenu">
          <img src="@/assets/img/cancel.svg" alt="" />
        </div>
        <ul class="burger__list">
          <li v-for="(item, index) in NAV_LIST" :key="index" class="nav__item">
            <a :href="item.link" class="nav_link">{{ item.label }}</a>
          </li>
        </ul>

        <a href="https://twitter.com/z0racles" class="twitter_btn">
          <span class="btn__text">Our twitter</span>
          <img src="@/assets/img/twitter.svg" alt="" class="btn__logo" />
        </a>
      </div>
    </div>
  </header>
</template>

<script>
import vClickOutside from "v-click-outside";

const NAV_LIST = [
  {
    label: "Home",
    link: "https://zoracles.com/"
  },
  {
    label: "Swap",
    link: "https://zoracles.com/"
  },
  {
    label: "Zora",
    link: "https://zoracles.com/"
  },
  {
    label: "Data",
    link: "https://data.zoracles.com"
  },
  {
    label: "Governance",
    link: "https://gov.zoracles.com"
  },
  {
    label: "Contract",
    link: "https://etherscan.io/token/0xd8e3fb3b08eba982f2754988d70d57edc0055ae6"
  }
];
export default {
  name: "Header",
  directives: {
    clickOutside: vClickOutside.directive
  },
  data() {
    return {
      NAV_LIST: NAV_LIST,
      scrollPosition: 0,
      isMenuOpened: false
    };
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY;
    },
    toggleMenu() {
      this.isMenuOpened = !this.isMenuOpened;
    },

    onClickOutside() {
      if (this.isMenuOpened) {
        this.isMenuOpened = false;
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  transition: 0.3s background-color ease-out;
  z-index: 200;
  background-color: inherit;
	padding: 20px 0 0 0;

  &.scrolled {
    background-color: var(--brend);
  }
    @media screen and (max-width: 991.98px) {
      padding: 0 30px 0;
    }
	@media screen and (max-width: 767px) {
    padding: 0 0;
  }
}
.header__container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  padding: 15px ;

  @media screen and (max-width: 767px) {
    padding: 15px 25px;
  }
}

.logo__container {
  max-width: 140px;
  display: flex;
  align-items: center;
  justify-content: center;

  img {
    width: 100%;
  }

  @media screen and (max-width: 767px) {
    max-width: 100px;
    margin-right: 16px;
  }
}

.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;

  @media screen and (max-width: 767px) {
    display: none;
  }
}

.nav__container {
  display: flex;
  list-style: none;
	padding: 0 90px;
}

.nav_link {
  font-family: "Lato";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  margin: 0 17px;
  text-decoration: none;
	position: relative;
	color: #fff; /*задаём цвет ссылки*/
	cursor: pointer;
}
.nav_link:after {
	display: block;
	position: absolute;
	left: 0; /*изменить на right:0;, чтобы изменить направление подчёркивания */
	width: 0;/*задаём длинну линии до наведения курсора*/
	height: 2px; /*задаём ширину линии*/
	background-color: #FF5547;
; /*задаём цвет линии*/
	content: "";
	transition: width 0.3s ease-out; /*задаём время анимации*/
}

.nav_link:hover:after,
.nav_link:focus:after {
	width: 100%; /*устанавливаем значение 100% чтобы ссылка подчёркивалась полностью*/
}

.buy_btn {
  margin-left: 20px;

  @media screen and (max-width: 767px) {
    margin: 0;
  }
}

.burger_menu {
  display: none;

  @media screen and (max-width: 767px) {
    display: block;
  }
}

.burger__list {
  list-style: none;
  padding: 0;
  margin-bottom: 16px;
  text-align: left;
  margin: 70px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  height: 60%;

  .nav_link {
    font-size: 28px;
    display: block;
  }
}

.burger {
  position: absolute;
  width: 18px;
  height: 16px;
  right: 20px;
  top: 24px;
  cursor: pointer;
  display: none;
  z-index: 12;

  @media screen and (max-width: 767px) {
    display: block;
  }

  img {
    width: 100%;
  }
}

.mobile__nav {
  display: none;
  position: absolute;
  right: 0;
  left: 0;
  top: 0;
  bottom: 0;
  background-color: #161F48;
  transform: translateY(-100%);
  transition: 0.3s all ease-out;
  height: 100vh;
  width: 100%;
  padding: 0 12px;
  z-index: 2000;

  &.active {
    transform: none;
  }

  @media screen and (max-width: 767px) {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}

.cross {
  position: absolute;
  width: 30px;
  height: 30px;
  right: 20px;
  top: 24px;
  cursor: pointer;
  z-index: 12;

  img {
    width: 100%;
  }
}

.twitter_btn {
  display: flex;
  padding: 9px 24px;
  background: #148dfd;
  border-radius: 25px;
  align-items: center;
  transition: 0.25 box-shadow ease-out;
  

  &:hover {
    box-shadow: 0px 2px 4px 3px #127adb;
  }

   @media screen and (max-width: 767px) {
    display: block;
    width: 160px;
  }
  .btn__text {
    margin-right: 8px;
    font-family: "Lato";
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 1.5;
    color: #ffffff;
  }

  .btn__logo {
    width: 15px;
  }
}
</style>
