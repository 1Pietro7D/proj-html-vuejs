<template>
  <main>
    <section class="blog_grid">
      <div class="max-container grid_col_3">
        <CardsComp v-for="x in gridBlogElement" :key="x.id" v-bind="x" />
      </div>
    </section>
  </main>
</template>

<script>
import { post } from "@/articles.js";
import { categoriesList } from "@/data.js";
import CardsComp from "./CardsComp.vue";
export default {
  name: "MainComp",
  data() {
    return {
      post,
      category: categoriesList,
      gridBlogElement: [],
    };
  },
  created() {
    this.getGridBlog(post);
  },
  methods: {
    getGridBlog(post) {
      for (
        let index = 0;
        this.gridBlogElement.length < 6 && index < post.length;
        index++
      ) {
        if (post[index].status == "top") {
          const element = post[index];
          this.gridBlogElement.push(element);
        }
      }
    },
  },
  components: { CardsComp },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
.blog_grid {
  padding: 2rem 0;
  background-color: $grey_theme;
}
</style>
