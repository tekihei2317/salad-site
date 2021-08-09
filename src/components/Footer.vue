<template>
  <footer>
    <div class="container">
      <div class="qr-block">
        <g-image :src="loadImage" />
      </div>
      <div class="logo-block">
        <div>
          <p class="site-name">SALAD SITE</p>
          <p class="site-name-ja">（サラダ・サイト）</p>
        </div>
        <p class="comment">テイクアウトも承っております</p>
      </div>
      <div class="contact-block">
        <p class="address">〒000-0000 愛知県豊田市細谷町4丁目488番地8号</p>
        <p class="building">サラダビル 2F</p>
        <p class="opening-hours">AM10:00 - PM15:00（月曜日~金曜日の平日営業中）</p>
        <p class="contact">
          <span>TEL: 000-0000-0000</span>
          <span> URL: https://example.com</span>
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  computed: {
    loadImage() {
      // TODO: 1カラムのとき画像の幅を大きくしたほうが良いかも
      return require("!!assets-loader?width=280!@images/qr-code.png");
    }
  }
};
</script>

<style lang="scss" scoped>
footer {
  background-color: #111111;
  color: white;
}
.container {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  align-items: center;
  padding: 4%;
}
.logo-block {
  padding-top: 32px;
}
.contact-block {
  padding-top: 32px;
}
@media (min-width: 1064px) {
  .container {
    flex-direction: row;
    justify-content: space-between;
    max-width: 1000px;
    margin: 0 auto;
    padding: 2rem 2rem;
  }
  // FIXME: グリッドレイアウトにすればこれが以下が不要になりそう
  .logo-block {
    padding-top: 0px;
  }
  .contact-block {
    padding-top: 0px;
  }
}

.logo-block {
  text-align: center;
  p {
    margin: 0;
  }
  .comment {
    margin-top: 16px;
    background-color: white;
    padding: 4px 8px;
    border-radius: 8px;
    color: black;
  }
}

// font
.logo-block {
  .site-name {
    font-size: 1.75rem;
    font-weight: bold;
  }
  .site-name-ja {
    font-weight: bold;
  }
  .comment {
    font-weight: bold;
  }
}
.contact-block {
  font-size: 1.1rem;
  p {
    margin: 0;
    padding-bottom: 8px;
  }
}
</style>
