<template>
  <nav>
    <ul class="d_flex gap_1">
      <li v-for="element in listLink" :key="element">
        <a :href="element.href">{{ element.label }}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Nav_comp",
  props: {
    listLink: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";

a {
  text-decoration: none;
  color: black;
}
</style>
