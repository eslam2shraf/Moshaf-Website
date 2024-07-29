<template>
  <topNav />
  <startPage />
  <threeApps />
  <AppsDescriptionVue />
</template>

<script>
import startPage from "./components/FirstSection.vue";
import threeApps from "./components/ThreeApps.vue";
import topNav from "./components/TopNav.vue";
import AppsDescriptionVue from "./components/AppsDescription.vue";

export default {
  name: "App",
  components: {
    topNav,
    startPage,
    threeApps,
    AppsDescriptionVue,
  },
};
</script>

<style>
body {
  background: #fef7ef;
}
</style>
