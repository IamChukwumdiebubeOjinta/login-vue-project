<script>
import NavBar from "./components/NavBar.vue";


export default {
  name: 'App',
  components: {
    NavBar,
  }
}
</script>

<template>
  <div class="h-screen  bg-gray-300">
    <NavBar />
    <routerView />
  </div>
</template>

<style scoped>
.login--body {
  min-height: 500px;
}
</style>
