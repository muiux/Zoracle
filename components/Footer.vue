<template>
  <div class="footer__container">
    <div class="intro">
      <div class="tabs info">
        <h2 class="template">zoracles</h2>
        <p>
          We are building a platform powered by Zoracles technology that
          empowers DeFi users with the data, tools and capital to be competitive
          in global decentralized financial markets.
        </p>
      </div>
      <div class="tabs quick__links">
        <h3 class="template">QUICK LINKS</h3>
        <ul class="list">
          <li><a class="link" href="https://zoracles.com/">Home</a></li>
          <li>
            <a class="link" href="https://zoraclesscribe.gitbook.io/zoracles/"
              >Docs</a
            >
          </li>
          <li><a class="link" href="https://nftswaps.org/">NFT Swap</a></li>
          <li>
            <a class="link" href="https://defiprime.com/zoracles">DeFi Prime</a>
          </li>
          <li>
            <a class="link" href="https://zoracles.com/whitepaper_v1.pdf"
              >Whitepaper</a
            >
          </li>
          <li><a class="link" href="https://github.com/zoracles">Github</a></li>
        </ul>
      </div>
      <div class="tabs more__links">
        <h3 class="template">MORE LINKS</h3>
        <ul class="list">
          <li>
            <a class="link" href="https://discord.com/invite/DSYQYAqEUX"
              >Discord</a
            >
          </li>
          <li><a class="link" href="https://t.me/zoracles">Telegram</a></li>
          <li>
            <a class="link" href="https://zoracles.medium.com/">Medium</a>
          </li>
          <li>
            <a class="link" href="https://twitter.com/z0racles">Twitter</a>
          </li>
          <li>
            <a class="link" href="https://www.reddit.com/r/Zoracles/">Reddit</a>
          </li>
          <li>
            <a
              class="link"
              href="https://www.youtube.com/channel/UCFx9FbUYK38_HhSm9DL38fQ"
              >YouTube</a
            >
          </li>
        </ul>
      </div>
      <div class="tabs subscribe">
        <h3 class="template">SUBSCRIBE</h3>
        <div class="form">
          <input
            class="input"
            type="email"
            placeholder="Enter your email"
            required
          />
          <button class="btn"><a href="#">Send</a></button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.footer__container {
  width: 100%;
  font-family: "RobotoCondensed";
  background-image: url(static/stars_section2.png);
  background-color: #131d41;
  color: #fff;
}

.template {
  margin-bottom: 16px;
}
.intro {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  text-align: left;
  padding: 60px 100px;

  @media screen and (max-width: 767px) {
    padding: 30px 16px;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  a {
    color: #fff;
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0.01em;
  }

  h3 {
    font-family: "RobotoCondensed";
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: 24px;
    letter-spacing: 0.01em;
  }
}
.tabs {
  background-image: url(static/stars_section2.png);
  background-color: #131d41;

  @media screen and (max-width: 767px) {
    text-align: center;
    margin-bottom: 32px;
  }
}
.info {
  list-style: none;
  text-decoration: none;
  color: #fff;

  @media screen and (max-width: 767px) {
    width: 100%;
  }

  .template {
    font-family: "Jockey";
    font-style: normal;
    font-weight: normal;
    font-size: 36px;
    line-height: 1;
    margin-bottom: 30px;

    @media screen and (max-width: 767px) {
      margin-bottom: 16px;
    }
  }

  p {
    color: rgba(255, 255, 255, 0.6);
    max-width: 300px;
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0.01em;
    text-align: left;

    @media screen and (max-width: 767px) {
      text-align: center;
      width: 100%;
	  margin: 0;
	  max-width: 100%;
    }
  }
}

.link:hover {
  color: #ff5547;
  transition: 0.5s;
}

.form {
  display: flex;
  flex-direction: row;

  @media screen and (max-width: 767px) {
      justify-content: center;
    }
}
.subscribe {
  width: 300px;
  background-image: url(static/stars_section2.png);
  background-color: #131d41;
}
.input {
  border-radius: 8px;
  background: #0d173e;
  color: #fff;
  font-size: 16px;
  height: 64px;
  width: 302px;
  text-indent: 25px;
  border: 0px;
}
input::placeholder {
  color: #fff;
}
.btn {
  background: #ff5547;
  color: #fff;
  font-size: 20px;
  height: 64px;
  width: 103px;
  border-radius: 8px;
  border: 0;
  transition: 0.25 box-shadow ease-out;

  &:hover {
    box-shadow: 0px 2px 4px 3px #cf2f21;
  }
}
.btn a {
  font-size: 20px;
}
@media screen and (max-width: 1200px) {
  .container .img__block {
    margin: 0 25px;
  }
  .input {
    font-size: 14px;
    height: 48px;
    width: 150px;
  }
  .btn {
    height: 46px;
    font-size: 16px;
    width: 75px;
  }
  .btn a {
    font-size: 20px;
  }
  .intro a {
    font-size: 14px;
  }
  .info p {
    font-size: 14px;
  }
}
@media screen and (max-width: 991.98px) {
  .container .img__block {
    margin: 0 25px;
  }
  .input {
    font-size: 14px;
    height: 48px;
    width: 150px;
  }
  .btn {
    height: 46px;
    font-size: 14px;
    width: 60px;
  }
  .info p {
    font-size: 12px;
  }
}
@media screen and (max-width: 576px) {
  .input {
    font-size: 12px;
    height: 46px;
    width: 130px;
  }
  .btn {
    font-size: 12px;
    height: 46px;
    width: 60px;
  }
}
</style>
