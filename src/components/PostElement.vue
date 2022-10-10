<template>
  <div class="d_flex pad_05">
    <img :src="require(`../assets/img/${image[0]}`)" alt="" />
    <div class="pad_05">
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
.d_flex {
  margin: 0 0.5rem;
  img {
    $size: 70px;
    width: $size;
    height: $size;
    object-fit: cover;
  }
}
</style>
