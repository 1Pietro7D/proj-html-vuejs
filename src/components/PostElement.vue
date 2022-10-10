<template>
  <div class="d_flex">
    <img :src="require(`../assets/img/${image[0]}`)" alt="" />
    <div>
      <h4>{{ title }}</h4>
      <p>{{ date }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "PostElement",
  props: {
    image: Array,
    title: String,
    author: String,
    date: String,
    article: String,
  },
  data() {
    return {
      images: this.image,
      imageRev: [],
    };
  },
  created() {
    this.getImageRev(this.images);
  },
  methods: {
    getImageRev(image) {
      this.imageRev = image.reverse();
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
img {
  $size: 70px;
  width: $size;
  height: $size;
  object-fit: cover;
}
</style>
