<template>
  <div class="container">
    <div class="info-top">
      <p class="title">Products you'll love</p>

      <a href="#" class="link">View all</a>

      <div class="options">
        <button @click="nxt" class="nxt">
          <i class="fas fa-arrow-left"></i>
        </button>
        <p>1 - 5</p>
        <button @click="prev" class="prev">
          <i class="fas fa-arrow-right"></i>
        </button>
      </div>
    </div>

    <div class="info-bottom" id="slide-offer">

      <div class="card" v-for="(item, index) in items" :key="index">
        <div class="imgBox">
          <img class="image" style="width:100%" :src="item.src" alt="product image">
          <div class="discount">{{item.discount}}</div>
        </div>
        <p class="product-name">{{item.name}}</p>
        <hr class="separator">
        <div class="priceBox">
          <p class="standar">Price</p>
          <p class="price">{{item.price}}</p>
        </div>

        <a href="#" class="btn-cart">Add to cart</a>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'CarouselOffer',

  data () {
    return {
      count: 0,
      items: [
        {
          src: require('../assets/products/product5.jpg'),
          name: 'Brownies with nuts',
          price: '8,18 €',
          discount: '-30%'
        },
        {
          src: require('../assets/products/product6.jpg'),
          name: 'Chocolate cake with strawberry',
          price: '11,23 €',
          discount: '-25%'
        },
        {
          src: require('../assets/products/product7.jpg'),
          name: 'Peanut butter',
          price: '4,50 €',
          discount: '-50%'
        },
        {
          src: require('../assets/products/product8.jpg'),
          name: 'Oreo cake',
          price: '18,71 €',
          discount: '-10%'
        },
        {
          src: require('../assets/products/product9.jpg'),
          name: 'Sweet bread',
          price: '20,50 €',
          discount: '-50%'
        },
        {
          src: require('../assets/products/product6.jpg'),
          name: 'Organic filled cereals - peanut butter & cacao',
          price: '11,23 €',
          discount: '-25%'
        },
        {
          src: require('../assets/products/product7.jpg'),
          name: 'Anti phone waves patch',
          price: '4,50 €',
          discount: '-50%'
        }
      ],
      frame: 2
    }
  },

  methods: {
    nxt () {
      this.count--
      this.scroll('prev')
    },
    prev () {
      this.count++
      this.scroll('nxt')
    },
    scroll (position) {
      const el = document.getElementById('slide-offer')
      let pos = 0
      const id = setInterval(frame, 5)
      const num = this.items.length - this.frame
      const width = 250
      const resize = num * width
      const check = position === 'reset' ? resize : width
      function frame () {
        if (pos === check) {
          clearInterval(id)
        } else {
          pos += 5
          if (position === 'nxt') {
            el.scrollLeft += 5
          } else {
            el.scrollLeft -= 5
          }
        }
      }
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
  margin-bottom: 30px;

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

  #slide-offer {
    display: flex;
    overflow: hidden;
    justify-content: space-between;
    align-items: flex-start;
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
      height: 570px;
      text-align: start;
      margin-right: 19px;

      .imgBox {
        width: 20em;
        .image {
          width: 100%;
          height: 100%;
        }

        .discount {
          width: 50px;
          height: 20px;
          background: rgb(102, 162, 240);
          position: relative;
          bottom: 40px;
          left: 10px;
          display: flex;
          justify-content: center;
          align-items: center;
          color: #f1f1f1;
          font-weight: 500;
        }
      }

      .product-name {
        min-width: 250px;
        min-height: 50px;
        font-size: 1.1rem;
        font-weight: 600;
      }

      .separator {
        border-style: dashed;
        color: rgb(216, 215, 215);
      }

      .priceBox {
        width: 100%;
        height: 50px;
        display: flex;
        justify-content: space-between;
        align-items: center;

        .standar {
          font-weight: 500;
        }
        .price {
          font-size: 1rem;
          font-weight: 700;
          color: #333;
        }
      }

      .btn-cart {
        width: 100%;
        height: 50px;
        background: #00c0bc;
        border-radius: 5px;
        display: flex;
        justify-content: center;
        align-items: center;
        color: #f1f1f1;
        font-weight: 500;
      }

      .btn-cart:hover {
        background: #03a5a2;
      }
    }
  }
}
</style>
