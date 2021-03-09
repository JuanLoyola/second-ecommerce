<template>
  <div class="container">
    <div class="home">
    <TheOne/>
  </div>
  </div>
</template>

<script>
import TheOne from '@/components/banners/TheOne.vue'

export default {
  name: 'Home',
  components: {
    TheOne
  }
}
</script>

<style lang="scss">
.container {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;

  .home {
    width: 65%;
  }
}

@media (max-width: 1300px) {
  .container {

    .home {
      width: 100%;
    }
  }
}
</style>
