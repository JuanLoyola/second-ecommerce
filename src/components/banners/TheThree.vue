<template>
  <div class="container">

    <div class="title">
      <p class="title">Shop by diet</p>
    </div>
      <div class="card" v-for="(item, index) in cards" :key="index" :style="{ 'background-color': item.color}">

      <div class="card-info">
        <p class="name">{{item.name}}</p>
        <p class="products"><span class="quantity">{{item.quantity}} </span> products</p>
        <a class="link" :href="item.url" target="_blank" rel="noopener noreferrer"><i class="fas fa-long-arrow-alt-right"></i></a>
      </div>

      <img class="card-logo" :src="item.image" alt="product image">
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheThree',

  data () {
    return {
      cards: [
        {
          quantity: '2657',
          name: 'vegan',
          url: '#',
          image: require('../../assets/images/vegan.png'),
          color: '#FFF6F2'
        },
        {
          name: 'protein',
          quantity: '229',
          url: '#',
          image: require('../../assets/images/protein.png'),
          color: '#edf3e3'
        },
        {
          name: 'gluten free',
          quantity: '1615',
          url: '#',
          image: require('../../assets/images/gluten.png'),
          color: '#fdf7dd'
        },
        {
          name: 'lactose free',
          quantity: '1916',
          url: '#',
          image: require('../../assets/images/lactose.png'),
          color: '#FFF6F2'
        },
        {
          name: 'organic',
          quantity: '2509',
          url: '#',
          image: require('../../assets/images/organic.png'),
          color: '#edf3e3'
        },
        {
          name: 'low in saturated fats',
          quantity: '814',
          url: '#',
          image: require('../../assets/images/fat.png'),
          color: '#fdf7dd'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  margin: 20px 0;
  width: 100%;
  display: flex;
  flex-flow: row wrap;

  .title {
    width: 100%;
    font-size: 1.7rem;
    font-weight: 600;
    margin-bottom: 30px;
  }

    .card {
      width: 370px;
      height: 140px;
      color: #72455F;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-flow: row nowrap;
      padding: 30px 30px;
      margin-right: 15px;
      margin-left: 15px;
      margin-bottom: 30px;
      box-shadow: 0px 1px 3px #bbbaba;
      border-radius: 7px;

      &-info {
        width: 100%;
        height: 100%;
        display: flex;
        flex-flow: column wrap;
        justify-content: space-evenly;
        text-transform: uppercase;

        .name {
          max-width: 250px;
          font-weight: 600;
          font-size: 1rem;
          letter-spacing: 2px;
        }

        .products {
          font-size: 0.7rem;
        }

        .quantity {
          font-weight: 600;
          font-size: 0.9rem;
          letter-spacing: 1.5px;
        }

        .link {
          color: #6bc6eb;

          &:hover {
            color: #0f739b;
          }
        }
      }

      &-logo {
        width: 45px;
        height: 45px;
      }
    }
}
</style>
