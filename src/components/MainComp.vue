<template>
  <main>
    <!-- section grid -->
    <section class="blog_grid">
      <div class="max-container grid_col_3">
        <CardsComp v-for="x in gridBlogElement" :key="x.id" v-bind="x" />
      </div>
    </section>
    <!-- /section grid -->
    <!-- Popular recent post section -->
    <section class="max-container grid_col_3 pad_y_2">
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
    <!-- Popular recent post section -->
    <!-- Nav category -->
    <aside class="navCategories">
      <div class="max-container d_flex">
        <div><font-awesome-icon icon="fa-solid fa-angle-left" /></div>
        <Nav_comp
          :listLink="category"
          :txWhite="true"
          class="flex_1"
          :paddingXl="true"
        />
        <div><font-awesome-icon icon="fa-solid fa-angle-right" /></div>
      </div>
    </aside>
    <!-- /Nav category -->
    <!-- Bakeka section -->
    <section class="bakeka">
      <div class="max-container d_flex pad_y_2">
        <!-- SIDE BAR LEFT -->
        <div class="bakeka">
          <ArticleComp v-for="x in popularBlogElement" :key="x.id" v-bind="x" />
        </div>

        <!-- SIDE BAR RIGHT -->
        <div class="side-bar">
          <!-- Twitter -->
          <div class="twitter">
            <h3 class="pad_y_1">latest from twitter</h3>
            <div class="d_flex mb_1">
              <font-awesome-icon icon="fa-brands fa-twitter" />
              <div class="ml_1">
                <p>
                  If you have any suggestions for the next updates, lets us
                  know.
                </p>
                <span>01:05 PM Sep 18th</span>
              </div>
            </div>
            <div class="d_flex">
              <font-awesome-icon icon="fa-brands fa-twitter" />
              <div class="ml_1">
                <p>
                  We have just update Porto Admin. Check the changelog for more
                  information.
                </p>
                <span>01:04 PM Sep 18th</span>
              </div>
            </div>
          </div>
          <!-- Instagram -->
        </div>
      </div>
    </section>
    <!-- Bakeka section -->
  </main>
</template>

<script>
import { post } from "@/articles.js";
import { categoriesList } from "@/data.js";
import CardsComp from "./CardsComp.vue";
import PostElement from "./PostElement.vue";
import Nav_comp from "./Nav_comp.vue";
import ArticleComp from "./ArticleComp.vue";
export default {
  name: "MainComp",
  data() {
    return {
      post,
      category: [],
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
    this.getCategoryList(categoriesList);
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
    getCategoryList(category) {
      for (let index = 0; index < 6; index++) {
        const element = category[index];
        this.category.push(element);
      }
    },
  },

  components: { CardsComp, PostElement, Nav_comp, ArticleComp },
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
  text-transform: uppercase;
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

.navCategories {
  background-color: $brand_theme;
  padding: 2.5rem 0;
  .max-container {
    * {
      margin: 0 1rem;
    }
  }
}
section.bakeka {
  margin: 0 1rem;

  .bakeka {
    width: 75%;

    height: 100px;
    margin-left: 1rem;
    margin-right: 1rem;
  }
  .side-bar {
    width: 25%;
    margin-left: 1rem;
    margin-right: 1rem;
    .twitter {
      p {
        color: $dark_grey;
      }
      span {
        color: $brand_theme;
      }
    }
  }
}
</style>
