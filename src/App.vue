<template>
  <div id="app">
    <HeaderComp />
    <MainComp />
    <FooterComp />
  </div>
</template>

<script>
import HeaderComp from "@/components/HeaderComp.vue";
import MainComp from "@/components/MainComp.vue";
import FooterComp from "@/components/FooterComp.vue";

export default {
  name: "App",
  components: {
    HeaderComp,
    MainComp,
    FooterComp,
  },
  data() {
    return {};
  },
  created() {},

  computed: {},
  methods: {},
  mounted() {},
};
</script>

<style lang="scss">
@import "@/assets/style/style.scss";
.max-container {
  max-width: 1200px;
  margin: auto;
}
</style>

<!--

@import "@/assets/style/generics.scss";
@import "@/assets/style/position.scss"; 
@import "@/assets/style/flex.scss";
@import "@/assets/style/grid.scss"; 

@import "@/assets/style/variables.scss";  !! this must be inserted into each component !!
-->
