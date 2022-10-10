<template>
  <nav>
    <ul class="d_flex gap_1 justify_around">
      <li
        :class="{ padXl: paddingXl == true }"
        v-for="(element, index) in listLink"
        :key="index"
      >
        <a :href="element.href" :class="{ txWhite: txWhite == true }">{{
          element.label
        }}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Nav_comp",
  props: {
    listLink: Array,
    txWhite: Boolean,
    paddingXl: Boolean,
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
li {
  display: inline-block;
}
a {
  text-decoration: none;
  color: black;
  text-transform: uppercase;
  &.txWhite {
    color: white;
  }
}
.padXl {
  > a {
    padding: 0.5rem 2rem;
    background-color: $paddin_dark_theme;
  }
}
</style>
