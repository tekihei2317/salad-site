<template>
  <div class="salad-container">
    <div class="salad-image">
      <g-image :src="loadImage" height="200" width="200" />
    </div>
    <div class="salad-info">
      <p>
        <span class="salad-name">{{ name }}</span>
        <span class="salad-price"> {{ price }}円</span>
      </p>
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
      return require(`!!assets-loader?width=240!@images/${this.imagePath}`);
    }
  }
};
</script>

<style lang="scss" scoped>
.salad-container {
  padding: 1em;
}

// font-size
.salad-container {
  /deep/ .salad-name {
    font-size: 1.5rem;
  }

  /deep/ .salad-price {
    font-size: 1.25rem;
  }

  /deep/ .salad-description {
    font-size: 1rem;
  }

  /deep/ .salad-ingredients {
    font-size: 0.85rem;
  }
}
</style>
