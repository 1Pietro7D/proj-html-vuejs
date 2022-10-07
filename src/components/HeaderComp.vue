<template>
  <header>
    <div id="navUtent_container">
      <Nav_comp :listLink="navUtent" />
    </div>
    <aside id="logo_container">
      <img src="@/assets/img/logo-default-slim.png" alt="logo header" />
    </aside>
    <div id="navApp_container">
      <Nav_comp :listLink="navApp" />
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
  div {
    padding: 1rem 0;
  }
  #navUtent_container {
    background-color: $navUtent_theme;
  }
}
#logo_container {
  padding: 2rem 0;
  border-bottom: 2px solid $grey_theme;
  img {
    height: 50px;
  }
}
</style>
