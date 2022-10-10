<template>
  <div class="cont relative">
    <div class="relative flex_col_rev gap_05">
      <p class="article">{{ shortArticle }}...</p>
      <h3 class="">{{ title }}</h3>
      <p class="category">{{ categories[0] }}</p>
    </div>
    <img
      class="absolute_0"
      :src="require(`../assets/img/${image[0]}`)"
      alt=""
    />
  </div>
</template>

<script>
export default {
  name: "CardComp",
  props: {
    image: Array,
    title: String,
    author: String,
    date: String,
    article: String,
    comments: Array,
    categories: Array,
  },
  data() {
    return {
      shortArticle: "",
    };
  },
  created() {
    this.getShortArticle(this.article);
  },
  methods: {
    getShortArticle(string) {
      for (let index = 0; index <= 70; index++) {
        this.shortArticle += string.charAt(index);
      }
      console.log(this.shortArticle);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
$pad: 1.5rem;
$mar: 1rem;
$size: 18vw;
.cont {
  background-color: aqua;
  height: $size;
  max-height: 200px;
  margin: $mar;
  div {
    background-color: rgba($color: #000000, $alpha: 0.5);
    color: white;
    height: calc($size - (($pad) * 2));
    max-height: calc(200px - (($pad) * 2));
    z-index: 1;
    padding: $pad;

    .article {
      display: none;
      color: $dark_grey;
    }
    h3 {
      font-weight: bolder;
    }
    .category {
      padding: 0.5rem;
      text-transform: uppercase;
      background-color: $brand_theme;
      font-size: small;
      border-radius: 5px;
      display: inline;
      align-self: flex-start;
    }
  }
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}
.cont:hover {
  scale: 1.1;
  div {
    border: 4px solid white;
    box-shadow: 5px 5px 5px #888888;
    box-sizing: content-box;
    height: calc($size - (($pad) * 2) - 8px);
    max-height: calc(200px - (($pad) * 2) - 8px);
    .article {
      display: initial;
    }
  }
}
</style>
