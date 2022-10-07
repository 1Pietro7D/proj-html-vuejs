<template>
  <nav>
    <ul class="d_flex gap_1">
      <li v-for="x in listLink" :key="x">
        <a :href="x.href">{{ x.label }}</a>
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
