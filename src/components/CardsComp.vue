<template>
  <div class="cont relative">
    <div class="relative flex_col_rev gap_05">
      <h3 class="">{{ title }}</h3>
      <p>{{ categories[0] }}</p>
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
    return {};
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
.cont {
  $pad: 2rem;
  $mar: 1rem;
  background-color: aqua;
  height: 13vw;
  margin: $mar;
  div {
    background-color: rgba($color: #000000, $alpha: 0.5);
    color: white;
    height: calc(13vw - (($pad) * 2));
    z-index: 1;
    padding: $pad;
    h3 {
      font-weight: bolder;
    }
    p {
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
</style>
