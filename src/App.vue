<template>
  <InfoBar></InfoBar>
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
}
</style>

<script>
import InfoBar from '@/components/InfoBar.vue'

export default {
  components: {
    InfoBar
  }
}
</script>
