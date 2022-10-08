<template>
  <main>
    <section class="blog_grid">
      <div class="max-container">
        <div v-for="(x, index) in gridBlogElement" :key="index">
          <p>{{ x.title }}</p>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import { post } from "@/articles.js";
import { categoriesList } from "@/data.js";
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
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
.blog_grid {
  padding: 2rem 0;
  background-color: $grey_theme;
}
</style>
