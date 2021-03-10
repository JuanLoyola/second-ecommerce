<template>
  <div class="container">
    <div class="info-left">
    <a>Referral program</a>
    </div>

    <div class="info-center">
      <a class="link" href="#">Delivery</a>
      <a class="link" href="#">Blog</a>
      <a class="link" href="#">Recipes</a>
      <a class="link" href="#">Gif Cards</a>
      <a class="link" href="#">Shopping guides</a>
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

  .info-left {
    font-size: 0.7rem;
    text-decoration: underline;
  }

  .info-center {
    display: flex;
    justify-content: space-evenly;
    width: 20%;
    font-weight: 500;

    .link {
      color: #f1f1f1;
      text-decoration: none;
    }

    .link:hover {
      color:#13C0A7
    }
  }

  .info-right {
    display: flex;
    justify-content: space-evenly;
    width: 5%;
  }
}

@media (max-width: 1300px) {
  .container {
    .info-center {
      display: none;
    }

    .info-right {
      display: none;
    }
  }
}
</style>
