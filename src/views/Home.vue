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

export default {
  name: 'Home',

  components: {
    TheOne,
    Carousel,
    CarouselSlide,
    TheStory,
    CarouselProduct,
    CarouselOffer,
    TheTwo
  },

  data () {
    return {
      slides: [
        'https://images.unsplash.com/photo-1605036927639-1555563331a9?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
        'https://images.unsplash.com/photo-1584305574647-0cc949a2bb9f?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
        'https://images.unsplash.com/photo-1535585209827-a15fcdbc4c2d?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80'
      ],
      visibleSlide: 0,
      direction: 'left'
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
  }
}

@media (max-width: 1300px) {
  .container {

    .home {
      width: 100%;

      .row {
        flex-flow: column;
      }
    }
  }
}
</style>
