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
    title: "Salad Site"
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
  font-size: 2.75rem;
  text-align: center;
  -webkit-text-stroke: 1.5px black;
  letter-spacing: 0.5rem;

  &--highlighted {
    font-size: 2.75rem;
    text-align: center;
    color: #4fae4f;
    margin-top: 16px;
    -webkit-text-stroke: 1.5px #4fae4f;
    letter-spacing: 0.5rem;
  }
}

.salad-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-auto-rows: 1fr;
}
</style>
