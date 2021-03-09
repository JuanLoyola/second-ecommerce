<template>
  <div class="container">
    <div class="info-left">
    <a>Referral program</a>
    </div>

    <div class="info-center">
      <a>Delivery</a>
      <a>Blog</a>
      <a>Recipes</a>
      <a>Gif Cards</a>
      <a>Shopping guides</a>
    </div>

    <div class="info-right">
      <a>EN</a>
      <a>Sign in</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'InfoBar'
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 35px;
  background:#3c4b5c;
  color: #f1f1f1;
  font-size: 0.8rem;
  font-weight: 500;
  display: flex;
  justify-content: space-evenly;

  .info-center {
    display: flex;
    justify-content: space-evenly;
    width: 20%;
    font-weight: 600;
  }

  .info-right {
    display: flex;
    justify-content: space-evenly;
    width: 5%;
  }
}
</style>
