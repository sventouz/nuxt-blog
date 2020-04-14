<template>
  <div class="tag">
    <div class="side__item">
      <p class="side__item__title">タグ</p>
      <div class="tags__wrapper">
        <ul class="tags">
          <li class=""><span>css (2)</span></li>
          <li class=""><span>database (1)</span></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.tag {
  margin-top: 30px;
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
  .tags__wrapper {
    padding: 10px 0;
  }
}
</style>
