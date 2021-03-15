<template>
  <InfoBar></InfoBar>
  <NavBar></NavBar>
  <router-view/>
</template>

<style lang="scss">
html {
  font-family: 'Montserrat', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 100%;
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  text-decoration: none;
}
</style>

<script>
import InfoBar from '@/components/InfoBar.vue'
import NavBar from '@/components/NavBar.vue'

export default {
  components: {
    InfoBar,
    NavBar
  }
}
</script>
