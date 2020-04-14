<template>
  <div class="profile">
    <div class="side__item">
      <p class="side__item__title">プロフィール</p>
      <div class="profile__wrap">
        <div class="profile__contents">
          <div class="profile__img"><img src="~/assets/profile.svg" width="15" height="15"></div>
          <div class="profile__body">
            <div class="profile__body__name">sventouz</div>
            <div class="profile__body__bio">vueとサウナが好きなフロントエンドエンジニア</div>
          </div>
        </div>
        <div class="profile__links">
          <a href="https://twitter.com/b_____san" target="_blank" class="profile__links__item"><img src="/_nuxt/img/ec8cceb.png"></a>
          <a href="https://github.com/b1san" target="_blank" class="profile__links__item"><img src="/_nuxt/img/f87561b.png"></a>
          <a href="https://qiita.com/b1san" target="_blank" class="profile__links__item"><img src="/_nuxt/img/bcbbbff.png"></a>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.profile {
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
  .profile__contents {
    display: flex;
    padding: 10px;
  }
  .profile__body {
    margin-left: 20px;
  }
  .profile__img {
    display: flex;
    align-items: center;
    justify-content: center;
    background: #fff;
    border-radius: 100px;
    height: 60px;
    margin-right: 5px;
    border: 1px solid #ddd;
    text-align: center;
  }
  .profile__img > img {
    border-radius: 100px;
    width: 60px;
  }
  .profile__body__name {
    font-weight: 700;
  }
  .profile__body__bio {
    color: #888;
    font-size: 13px;
    margin-top: 5px;
  }
}
</style>
