<template>
  <div class="salad-container">
    <div class="salad-image">
      <g-image :src="loadImage" height="200" width="200" />
    </div>
    <div class="salad-info">
      <div>
        <span class="salad-name">{{ name }}</span>
        <span class="salad-price">¥{{ price }}</span>
        <p class="salad-japanese-name">{{ japaneseName }}</p>
      </div>
      <p class="salad-description">{{ description }}</p>
      <p class="salad-ingredients">{{ ingredients.join("/") }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    },
    price: {
      type: Number,
      required: true
    },
    japaneseName: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    ingredients: {
      type: Array,
      required: true
    },
    imagePath: {
      type: String,
      required: true
    }
  },
  computed: {
    loadImage() {
      // TODO: 1カラムのとき画像の幅を大きくしたほうが良いかも
      return require(`!!assets-loader?width=280&blur=1!@images/${this.imagePath}`);
    }
  }
};
</script>

<style lang="scss" scoped>
.salad-container {
  padding: 2em;
}

.salad-image {
  text-align: center;
}

.salad-price {
  margin-left: 16px;
}

.salad-japanese-name {
  margin-top: 0px;
}
// font
.salad-container {
  /deep/ .salad-name {
    font-size: 1.5rem;
    font-weight: bold;
  }
  /deep/ .salad-price {
    font-size: 1.25rem;
    font-weight: bold;
  }
  /deep/ .salad-japanese-name {
    font-size: 0.85rem;
    font-weight: bold;
  }
  /deep/ .salad-description {
    font-size: 0.9rem;
    font-weight: bold;
  }
  /deep/ .salad-ingredients {
    font-size: 0.85rem;
  }
}
</style>
