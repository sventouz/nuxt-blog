<template>
  <div class="latest">
    <div class="side__item">
      <p class="side__item__title">最新記事</p>
      <ul class="side__posts">
        <li>
          <img src="https://images.ctfassets.net/j66nvsb0pq4h/44XLnqISCrFFY3bjJ7UGxx/535de293a223daa4a662384628bf58d9/nuxt.png">
          <p class="side__posts__title">Nuxt.js ルーティングの基礎を学ぼう</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<style lang="scss">
.latest {
  margin-top: 30px;
  .side__item {
    background: #fff;
    box-shadow: 2px 2px 5px rgba(0,0,0,.2);
  }
  .side__item {
    background: #fff;
    box-shadow: 2px 2px 5px rgba(0,0,0,.2);
  }
  .side__item__title {
    background: #00bf8a;
    color: #fff;
    font-size: 16px;
    font-weight: 700;
    line-height: 30px;
    text-align: center;
  }
  .side__posts {
    padding: 0;
  }
  .side__posts > li {
    padding: 10px;
    display: flex;
    cursor: pointer;
    transition: opacity .4s;
  }
  .side__posts > li > img {
    display: block;
    width: 45px;
    height: 45px;
  }
  .side__posts__title {
    margin-left: 10px;
    font-size: 14px;
    font-weight: 700;
  }
}
</style>
