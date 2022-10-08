<template>
  <main>
    <div></div>
  </main>
</template>

<script>
import { post } from "@/articles.js";
import { categoriesList } from "@/data.js";
export default {
  name: "MainComp",
  data() {
    return { post, category: categoriesList };
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
</style>
