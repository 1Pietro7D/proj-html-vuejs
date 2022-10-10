<template>
  <main>
    <section class="blog_grid">
      <div class="max-container grid_col_3">
        <CardsComp v-for="x in gridBlogElement" :key="x.id" v-bind="x" />
      </div>
    </section>
    <section class="max-container grid_col_3">
      <div>
        <h3>POPULAR POST</h3>
        <PostElement v-for="x in popularBlogElement" :key="x.id" v-bind="x" />
      </div>
      <div>
        <h3>RECENT POST</h3>
        <PostElement v-for="x in recentBlogElement" :key="x.id" v-bind="x" />
      </div>
      <div>
        <h3>FEATURES POST</h3>
        <CardsComp v-for="x in featuresBlogElement" :key="x.id" v-bind="x" />
        <h3>FEATURED AUTHOR</h3>
        <div class="author d_flex pad_05">
          <img src="@/assets/img/avatar.jpg" alt="author" />
          <div class="pad_05">
            <h4>John Doe</h4>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit.
              Suscipit, assume
            </p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import { post } from "@/articles.js";
import { categoriesList } from "@/data.js";
import CardsComp from "./CardsComp.vue";
import PostElement from "./PostElement.vue";
export default {
  name: "MainComp",
  data() {
    return {
      post,
      category: categoriesList,
      gridBlogElement: [],
      featuresBlogElement: [],
      popularBlogElement: [],
      recentBlogElement: [],
    };
  },
  created() {
    this.getGridBlog(post);
    this.getFeaturesBlog(post);
    this.getPopularBlog(post);
    this.getRecentBlog(post);
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
    getFeaturesBlog(post) {
      for (
        let index = 0;
        this.featuresBlogElement.length < 1 && index < post.length;
        index++
      ) {
        if (post[index].id == "13") {
          const element = post[index];
          this.featuresBlogElement.push(element);
        }
      }
    },
    getPopularBlog(post) {
      for (
        let index = 0;
        this.popularBlogElement.length < 5 && index < post.length;
        index++
      ) {
        if (post[index].status == "popular") {
          const element = post[index];
          this.popularBlogElement.push(element);
        }
      }
    },
    getRecentBlog(post) {
      for (
        let index = 0;
        this.recentBlogElement.length < 5 && index < post.length;
        index++
      ) {
        if (post[index].status == "recent") {
          const element = post[index];
          this.recentBlogElement.push(element);
        }
      }
    },
  },

  components: { CardsComp, PostElement },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
.blog_grid {
  padding: 2rem 0;
  background-color: $grey_theme;
}
h3 {
  padding: 1rem;
}
.author {
  margin: 0 0.5rem;
  img {
    $size: 120px;
    width: $size;
    height: $size;
    object-fit: cover;
  }
}
</style>
