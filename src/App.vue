<template>
  <header class="d-flex">
    <div class="logo-container d-flex align-items-center">
      <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/Yu-Gi-Oh%21.png" alt="yu-gi-oh logo">
    </div>
    <h1>
      Yu-Gi-Oh Api
    </h1>
  </header>
  <AppMain />
</template>

<script>
import AppMain from "./components/AppMain.vue";

 export default {
  name: "App",
  components: {
    AppMain
  }
 }
</script>

<style lang="scss">
  @use "./style/general.scss" as *;
</style>
