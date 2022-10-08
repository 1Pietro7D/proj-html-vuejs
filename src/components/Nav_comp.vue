<template>
  <nav>
    <ul class="d_flex gap_1">
      <li v-for="(element, index) in listLink" :key="index">
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
  },
};
</script>

<style lang="scss" scoped>
a {
  text-decoration: none;
  color: black;
  text-transform: uppercase;
  &.txWhite {
    color: white;
  }
}
</style>
