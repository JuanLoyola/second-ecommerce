<template>
  <div class="container">
    <div class="info-top">
      <p class="title">Shopping guides</p>

      <a href="#" class="link">View all</a>

      <div class="options">
        <button @click="next" class="next">
          <i class="fas fa-arrow-left"></i>
        </button>
        <p>1 - 10</p>
        <button @click="prev" class="prev">
          <i class="fas fa-arrow-right"></i>
        </button>
      </div>
    </div>

    <div class="info-bottom">

      <div class="card">
        <div class="imgBox">
          <img class="image" src="@/assets/images/product1.jpg" alt="product image">
        </div>
        <p class="quantity">17 products</p>
        <p class="product-name">The best for your health</p>
      </div>

      <div class="card">
        <div class="imgBox">
          <img class="image" src="@/assets/images/product2.jpg" alt="product image">
        </div>
        <p class="quantity">11 products</p>
        <p class="product-name">Our gluten-free selection</p>
      </div>

      <div class="card">
        <div class="imgBox">
          <img class="image" src="@/assets/images/product3.jpg" alt="product image">
        </div>
        <p class="quantity">25 products</p>
        <p class="product-name">Clean home essentials</p>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'CarouselProduct',

  methods: {
    next () {
      this.$emit('next')
    },
    prev () {
      this.$emit('prev')
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  max-width: 100%;
  display: flex;
  flex-flow: column nowrap;
  overflow: hidden;

  .info-top {
    width:100%;
    height: 50px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #000;

    .title {
      font-size: 1.6rem;
      font-weight: 600;
    }

    .link {
      font-size: 0.9rem;
      font-weight: 600;
      color: #a571d6;
    }

    .link:hover {
      color: #8558af;
    }

    .options {
      width: 250px;
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      font-weight: 600;

      button{
        height: 40px;
        width: 50px;
        top: calc(50% - 20px);
        background-color: rgba(0, 0, 0, 0.7);
        border: none;
        color: #fff;
      }

      button:focus,
      button:hover {
        outline: none;
        cursor: pointer;
        background-color: rgba(0, 0, 0, 0.5);
      }
    }
  }

  .info-bottom {
    width: 100%;
    margin: 30px 0;
    display: flex;
    justify-content: space-between;
    flex-flow: row nowrap;

    .card {
      display: flex;
      flex-flow: column;
      justify-content: space-between;
      height: 350px;
      text-align: start;

      .imgBox {
        width: 25em;
        .image {
          width: 100%;
          height: 100%;
        }
      }

      .quantity {
        font-size: 0.8rem;
        font-weight: 700;
        color: #b6b6b6;
      }

      .product-name {
        font-size: 1.4rem;
        font-weight: 600;
      }
    }
  }
}
</style>
