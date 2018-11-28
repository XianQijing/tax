<template>
  <div class="home">
    <home-header></home-header>
    <home-body></home-body>
  </div>
</template>

<script>
import HomeHeader from './components/header'
import HomeBody from './components/body'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeBody
  }
}
</script>

<style scoped>
.home {
  height: 100%;
}
.body {
  height: calc(100% - 100px);
  box-sizing: border-box;
}
</style>
