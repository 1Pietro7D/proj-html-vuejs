<template>
  <header>
    <div class="navUtent">
      <div class="max-container d_flex gap_1 pad_y_1">
        <p>Everything about Lifestyle, Travel and Gadgets!</p>
        <Nav_comp :listLink="navUtent" :txWhite="true" />
      </div>
    </div>
    <aside class="logo">
      <div class="max-container pad_y_2">
        <img src="@/assets/img/logo-default-slim.png" alt="logo header" />
      </div>
    </aside>
    <div class="navApp">
      <div class="max-container d_flex justify_between pad_y_1">
        <Nav_comp :listLink="navApp" />
        <font-awesome-icon icon="fa-solid fa-search" />
      </div>
    </div>
  </header>
</template>

<script>
import { navUtent } from "@/data.js";
import { navApp } from "@/data.js";
import Nav_comp from "./Nav_comp.vue";
export default {
  name: "HeaderComp",
  props: {},
  data() {
    return { navUtent, navApp };
  },
  components: {
    Nav_comp,
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
header {
  .navUtent {
    background-color: $navUtent_theme;
    color: white;
    a {
      color: white;
    }
  }
}

.logo {
  border-bottom: 2px solid $grey_theme;
  img {
    height: 50px;
  }
}
</style>
