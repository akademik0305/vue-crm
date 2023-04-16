<template>
  <div id="app">
    <component :is="layout">
      <router-view />
      <!-- <empty-layout></empty-layout> -->
      <!-- <main-layout></main-layout> -->
    </component>
  </div>
</template>

<script>
import EmptyLayout from "./layouts/EmptyLayout.vue";
import MainLayout from "./layouts/MainLayout.vue";
// import HistoryViewVue from "./views/HistoryView.vue";
// import HomeView from "./views/HomeView.vue";
export default {
  computed: {
    layout() {
      console.log(this.$route.meta);
      return (this.$route.meta.layout || "main") + "-layout";
    },
  },
  components: {
    EmptyLayout,
    MainLayout,
  },
};
</script>

<style lang="scss">
@import "~materialize-css/dist/css/materialize.min.css";
@import "@/assets/index.css";
</style>
