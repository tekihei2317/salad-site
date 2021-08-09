<template>
  <div class="salad-container">
    <div class="salad-info">
      <div>
        <span class="salad-name">{{ name }}</span>
        <span class="salad-price">¥{{ price }}</span>
        <p class="salad-japanese-name">{{ japaneseName }}</p>
      </div>
      <p class="salad-description">{{ description }}</p>
      <p class="salad-ingredients">{{ ingredients.join("/") }}</p>
    </div>
    <div class="salad-image">
      <g-image :src="loadImage" />
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
      return require(`!!assets-loader?width=480!@images/${this.imagePath}`);
    }
  }
};
</script>

<style lang="scss" scoped>
.salad-container {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column-reverse;
}
@media (min-width: 768px) {
  .salad-container {
    flex-direction: row;
  }

  .salad-info {
    flex: 1;
    padding-top: 120px;
  }
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
    font-size: 1.75rem;
    font-weight: bold;
  }
  /deep/ .salad-price {
    font-size: 1.5rem;
    font-weight: bold;
  }
  /deep/ .salad-japanese-name {
    font-size: 1rem;
    font-weight: bold;
  }
  /deep/ .salad-description {
    font-size: 1rem;
    font-weight: bold;
  }
  /deep/ .salad-ingredients {
    font-size: 1rem;
  }
}
</style>
