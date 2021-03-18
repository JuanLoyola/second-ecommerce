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
        <button @click="previous" class="prev">
          <i class="fas fa-arrow-right"></i>
        </button>
      </div>
    </div>

    <div class="info-bottom" id="slide">

      <div class="card" v-for="(item, index) in items" :key="index">
        <div class="imgBox">
          <img class="image" style="width:100%" :src="item.src" alt="product image">
        </div>
        <p class="quantity">{{item.quantity}}</p>
        <p class="product-name">{{item.name}}</p>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'CarouselProduct',

  data () {
    return {
      count: 0,
      items: [
        {
          src: require('../assets/images/product1.jpg'),
          name: 'The best for your health',
          quantity: '17 products'
        },
        {
          src: require('../assets/images/product2.jpg'),
          name: 'Our gluten-free selection',
          quantity: '11 products'
        },
        {
          src: require('../assets/images/product3.jpg'),
          name: 'Clean home essentials',
          quantity: '25 products'
        },
        {
          src: require('../assets/images/product2.jpg'),
          name: 'The best for your health',
          quantity: '6 products'
        }
      ],
      frame: 2
    }
  },

  methods: {
    next () {
      this.count--
      this.scroll('previous')
    },
    previous () {
      this.count++
      this.scroll('next')
    },
    scroll (position) {
      const el = document.getElementById('slide')
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
          if (position === 'next') {
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

  #slide {
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
      height: 350px;
      text-align: start;
      margin-right: 20px;

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
