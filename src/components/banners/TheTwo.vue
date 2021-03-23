<template>
  <div class="container">
    <p class="title">Buy profitably with the membership</p>

    <div class="container-info">

      <div class="items">
        <img class="image"  src="@/assets/images/sale.svg" alt="icon">
        <p class="info">Discounts of <span class="important">up to 50%</span> on all the products</p>
      </div>

      <div class="items center">
        <img class="image"  src="@/assets/images/apple.svg" alt="icon">
        <p class="info">A<span class="important"> healthy</span> and sustainable life for an amazing price</p>
      </div>

      <div class="items">
        <img class="image" src="@/assets/images/box.svg" alt="icon">
        <p class="info">Wonderful surprises <span class="important">all year</span> long</p>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'TheTwo'
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  display: flex;
  flex-flow: column nowrap;
  justify-content: flex-start;
  align-items: flex-start;

  .title {
    text-align: start;
    font-weight: 600;
    font-size: 1.4rem;
    margin-bottom: 30px;
  }

  &-info {
    width: 100%;
    height: 260px;
    background-color: #FFF6F2;
    display: flex;
    justify-content: space-between;
    align-items: center;

    .items {
      display: flex;
      justify-content: space-between;
      align-items: center;

      .image {
        width: 125px;
        height: 125px;
      }

      .info {
        font-weight: 600;
        font-size: 1.2rem;
      }

      .important {
        color: #FD854F;
      }
    }

    .center {
      border-left: 2px dashed #bdbdbd;
      border-right: 2px dashed #bdbdbd;
    }
  }
}

@media (max-width: 1024px) {
  .container {

    &-info {
      height: 560px;
      display: flex;
      flex-flow: column nowrap;
      justify-content: space-evenly;

      .items {
        display: flex;
        justify-content: space-between;
        align-items: center;

        .image {
          width: 125px;
          height: 125px;
        }

        .info {
          font-weight: 600;
          font-size: 1.2rem;
        }

        .important {
          color: #FD854F;
        }
      }

      .center {
        border-top: 2px dashed #bdbdbd;
        border-bottom: 2px dashed #bdbdbd;
        border-left: none;
        border-right: none;
      }
    }
  }
}
</style>
