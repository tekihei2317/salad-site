<template>
  <Layout>
    <div class="page-body">
      <div class="page-top">
        <h2 class="primary-text">新鮮な無農薬野菜を中心とした</h2>
        <h2 class="primary-text--highlighted">デリバリーサラダ専門店</h2>
      </div>
      <div class="most-popular-salad">
        <primary-salad
          :key="primarySalad.name"
          :name="primarySalad.name"
          :price="primarySalad.price"
          :japaneseName="primarySalad.japaneseName"
          :description="primarySalad.description"
          :ingredients="primarySalad.ingredients"
          :imagePath="primarySalad.imagePath"
        />
      </div>
      <div class="salad-list">
        <template v-for="salad in saladList">
          <mini-salad
            :key="salad.name"
            :name="salad.name"
            :price="salad.price"
            :japaneseName="salad.japaneseName"
            :description="salad.description"
            :ingredients="salad.ingredients"
            :imagePath="salad.imagePath"
          />
        </template>
      </div>
    </div>
  </Layout>
</template>

<script>
import PrimarySalad from "~/components/PrimarySalad";
import MiniSalad from "~/components/MiniSalad";

import { primarySalad, saladList } from "~/constants/saladList";

export default {
  components: {
    PrimarySalad,
    MiniSalad
  },

  metaInfo: {
    title: "Hello, world!"
  },

  data() {
    return {
      primarySalad: primarySalad,
      saladList: saladList
    };
  }
};
</script>

<style lang="scss" scoped>
.primary-text {
  &--highlighted {
    color: #4fae4f;
  }
}
</style>
