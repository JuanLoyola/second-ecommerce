<template>
  <div class="container">
    <div class="home">
    <TheOne/>
    <div class="row">
      <Carousel
        @next="next"
        @prev="prev"
        >
          <Carousel-slide
            v-for="(slide, index) in slides"
            :key="slide"
            :index="index"
            :visibleSlide = "visibleSlide"
            :direction = "direction"
            >
            <img class="img" :src="slide">
          </Carousel-slide>
      </Carousel>
      <TheStory />
    </div>
    <CarouselProduct></CarouselProduct>
    <CarouselOffer></CarouselOffer>
    <TheTwo></TheTwo>
    <div class="tabs">
      <Tabs :tabs="['Organic', 'No refined sugar', 'Sustainable', 'Cruelty free', 'Additives free']" :selected="selected" @selected="setSelected" >
      <Tab :isSelected="selected === 'Organic'" >
        <div class="tab-info organic">
          <p class="tab-title">Organic</p>
          <p class="tab-content">Eating organic food is extremely important to anyone willing to eat clean food and avoid toxic ingredients. Non-organic food tend to be full of pesticides, and we do not want that for our customers at Kazidomi, which is why we are promoting organic sourcing wherever it makes sense. Indeed, this doesn't apply to some categories like food supplement, but there, we make sure other strict criteria are always fulfiled.</p>
          <a href="#" class="tab-button">Learn more</a>
        </div>
      </Tab>
      <Tab :isSelected="selected === 'No refined sugar'" >
        <div class="tab-info sugar">
          <p class="tab-title">No refined sugar</p>
          <p class="tab-content">Refined sugar and artificial sweeteners are one of the key dietary issues in the 21st century. At Kazidomi, we have the ambition to fight it. For this reason, our products don't contain refined sugar and have been selected for their use of minimum added sugar and under their best natural forms, like coconut sugar for instance.</p>
          <a href="#" class="tab-button">Learn more</a>
        </div>
      </Tab>
      <Tab :isSelected="selected === 'Sustainable'" >
        <div class="tab-info sustainable">
          <p class="tab-title">Sustainable</p>
          <p class="tab-content">The brands we work with are selected because their care for the environment. They can do this in multiple ways, from reducing unnecessary packaging to sourcing local ingredients. In any case, this is a cause we care deeply about and pay attention to in order to make sure our suppliers do too. Our logistics is just as green as our products, because we only use recyclable packaging materials and target a zero-waste warehouse going froward.</p>
          <a href="#" class="tab-button">Learn more</a>
        </div>
      </Tab>
      <Tab :isSelected="selected === 'Cruelty free'" >
        <div class="tab-info cruelty">
          <p class="tab-title">Cruelty free</p>
          <p class="tab-content">We love animals, and we want to make sure that we avoid promoting any mistreatment in the products we sell. This means that our cosmetics are not tested on animals, and that we promote animal food substitute to encourage plant-based diets.</p>
          <a href="#" class="tab-button">Learn more</a>
        </div>
      </Tab>
      <Tab :isSelected="selected === 'Additives free'" >
        <div class="tab-info additives">
          <p class="tab-title">Additives free</p>
          <p class="tab-content">At Kazidomi, we love short lists of ingredients that are free of any suspicious additives. Indeed, we favour natural products that don't need preservatives and additives. Natural living is the best way to have a healthy body.</p>
          <a href="#" class="tab-button">Learn more</a>
        </div>
      </Tab>
    </Tabs>
    </div>
    <TheThree></TheThree>
  </div>
  </div>
</template>

<script>
import TheOne from '@/components/banners/TheOne.vue'
import Carousel from '../components/Carousel.vue'
import CarouselSlide from '@/components/CarouselSlide.vue'
import TheStory from '@/components/banners/TheStory.vue'
import CarouselProduct from '@/components/CarouselProduct.vue'
import CarouselOffer from '@/components/CarouselOffer.vue'
import TheTwo from '@/components/banners/TheTwo.vue'
import Tab from '@/components/tabs/Tab.vue'
import Tabs from '@/components/tabs/Tabs.vue'
import TheThree from '@/components/banners/TheThree.vue'

export default {
  name: 'Home',

  components: {
    TheOne,
    Carousel,
    CarouselSlide,
    TheStory,
    CarouselProduct,
    CarouselOffer,
    TheTwo,
    Tab,
    Tabs,
    TheThree
  },

  data () {
    return {
      slides: [
        'https://images.unsplash.com/photo-1605036927639-1555563331a9?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
        'https://images.unsplash.com/photo-1584305574647-0cc949a2bb9f?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
        'https://images.unsplash.com/photo-1535585209827-a15fcdbc4c2d?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80'
      ],
      visibleSlide: 0,
      direction: 'left',
      selected: 'Organic'
    }
  },

  computed: {
    slidesLen () {
      return this.slides.length
    }
  },

  methods: {
    next () {
      if (this.visibleSlide >= this.slidesLen - 1) {
        this.visibleSlide = 0
      } else {
        this.visibleSlide++
      }
      this.direction = 'left'
    },
    prev () {
      if (this.visibleSlide <= 0) {
        this.visibleSlide = this.slidesLen - 1
      } else {
        this.visibleSlide--
      }
      this.direction = 'right'
    },
    setSelected (tab) {
      this.selected = tab
    }
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

    .img {
      width: 100%;
      height: 100%;
    }

    .row {
      width: 100%;
      display: flex;
      flex-flow: row nowrap;
      justify-content: space-between;
      align-items: center;
      margin: 30px 0;
    }

    .tab-info {
      width: 100%;
      height: 430px;
      padding: 50px 60px;
      display: flex;
      justify-content: space-around;
      flex-flow: column nowrap;
      color: #f1f1f1;
      background: red;
      text-align: start;
    }

    .tab-title {
      font-size: 2.3rem;
      font-weight: 600;
    }

    .tab-content {
      max-width: 45%;
      font-size: 1rem;
      font-weight: 500;
      line-height: 25px;
    }

    .tab-button {
      color: #f1f1f1;
      background-color: #00c0bc;
      max-width: 250px;
      height: 50px;
      border-radius: 5px;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .organic {
      background-image: url('../assets/images/multiple/multi1.jpg');
      background-size: cover;
      background-repeat: no-repeat;
    }

    .sugar {
      background-image: url('../assets/images/multiple/multi2.jpg');
      background-size: cover;
      background-repeat: no-repeat;
      color: #333;
    }

    .sustainable {
      background-image: url('../assets/images/multiple/multi3.jpg');
      background-size: cover;
      background-repeat: no-repeat;
      color: #333;
    }

    .cruelty {
      background-image: url('../assets/images/multiple/multi4.jpg');
      background-size: cover;
      background-repeat: no-repeat;
      color: #333;
    }

    .additives {
      background-image: url('../assets/images/multiple/multi5.jpg');
      background-size: cover;
      background-repeat: no-repeat;
      color: #333;
    }
  }
}

@media (max-width: 1300px) {
  .container {

    .home {
      width: 100%;

      .row {
        flex-flow: column;
      }

      .tabs {
        display: none;
      }
    }
  }
}
</style>
