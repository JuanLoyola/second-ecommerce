<template>
  <div class="carousel">
    <slot></slot>
    <button @click="next" class="next">
      <i class="fas fa-arrow-right"></i>
    </button>
    <button @click="prev" class="prev">
      <i class="fas fa-arrow-left"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: 'Carousel',

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
.carousel {
  position: relative;
  width: 600px;
  height: 350px;
  overflow: hidden;
  margin: 30px 0;

  button{
    position: absolute;
    height: 40px;
    width: 50px;
    top: calc(50% - 20px);
    background-color: rgba(0, 0, 0, 0.5);
    border: none;
    color: #fff;
  }

  button:focus,
  button:hover {
    outline: none;
    cursor: pointer;
  }

  .next {
    right: 0;
  }

  .prev {
    left: 0;
  }
}

@media (max-width: 1300px) {
  .carousel {
    position: relative;
    width: 100%;
  }
}
</style>
