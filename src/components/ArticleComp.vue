<template>
  <article class="pad_bot_2 pad_top_1">
    <img
      class="pad_bot_1"
      :src="require(`../assets/img/${imageRev[0]}`)"
      alt=""
    />
    <div class="d_flex">
      <div class="calendar mr_1">
        <div class="day">12</div>
        <div class="mounth">Jan</div>
      </div>
      <div class="content grow_1">
        <h2 class="pad_bot_1">{{ title }}</h2>
        <p class="pad_bot_1">{{ article }}</p>
        <div class="d_flex justify_between pad_bot_1 align_center border-bot">
          <div class="d_flex gap_1">
            <div class="author d_flex gap_05">
              <font-awesome-icon icon="fa-regular fa-user" />
              By <span>{{ author }}</span>
            </div>
            <div class="category d_flex gap_05">
              <font-awesome-icon icon="fa-regular fa-folder" />
              <span v-for="(category, index) in categories" :key="index"
                >{{ category }}
              </span>
            </div>
            <div class="category d_flex gap_05">
              <font-awesome-icon icon="fa-regular fa-comments" />
              <span>{{ comments.length }} comments</span>
            </div>
          </div>
          <div class="my-btn">READ MORE</div>
        </div>
      </div>
    </div>
  </article>
</template>

<script>
export default {
  name: "ArticleComp",
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
      images: this.image,
      imageRev: [],
    };
  },
  created() {
    this.getImageRev(this.images);
  },
  methods: {
    getImageRev(image) {
      console.log(this.imageRev);
      this.imageRev = image.reverse();
      console.log(this.imageRev);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
.my-btn {
  padding: 0.5rem;
  border: 1px solid $dark_grey;
  border-radius: 3px;
  color: $dark_grey;
  font-size: small;
}
.day {
  padding: 1rem;
  background: $dark_grey;
}
.mounth {
  padding: 0.25rem;
  background-color: black;
  color: white;
  text-align: center;
  text-transform: uppercase;
  font-size: smaller;
}
img {
  width: 100%;
  height: 20vw;
  object-fit: cover;
}
.border-bot {
  border-bottom: 2px solid rgb(212, 212, 212);
}
.content {
  span {
    color: $brand_theme;
  }
}
</style>
