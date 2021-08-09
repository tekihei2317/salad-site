<template>
  <div>
    <g-image :src="loadImage" height="400" width="400" />
    <p>
      <span>{{ name }}</span>
      <span> {{ price }}円</span>
    </p>
    <p>{{ description }}</p>
    <p>{{ ingredients.join("/") }}</p>
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
