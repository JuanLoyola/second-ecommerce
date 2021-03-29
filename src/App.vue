<template>
  <InfoBar></InfoBar>
  <NavBarMobile />
    <div class="content" :class="{'open':showNav}">
      <div class="top-bar">
        <div id="navigation-icon" v-if="mobileView"
          @click="showNav = !showNav">
          <i class="fas fa-bars"></i>
        </div>
        <NavBar v-if="!mobileView" />
      </div>
      <router-view/>
    <TheFooter></TheFooter>
    </div>
</template>

<style lang="scss">
html {
  font-family: 'Montserrat', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 100%;
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  text-decoration: none;
}
.top-bar {
  display: flex;
  width: 100%;
}
#navigation-icon {
  padding: 10px 10px 20px;
  margin-right: 10px;
  cursor: pointer;
  i {
    font-size: 2rem;
  }
}
.content {
  position: absolute;
  top: 35px;
  width: 100%;
  padding: 0px;
  background-color: #fff;
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  transition: 1s transform cubic-bezier(0,.12,.14,1);
}
.open {
  transform: translateX(300px);
}
@media (min-width: 1300px) {
  .content {
    padding: 0px;
  }
}
</style>

<script>
import InfoBar from '@/components/InfoBar.vue'
import NavBar from '@/components/NavBar.vue'
import NavBarMobile from '@/components/NavBarMobile.vue'
import TheFooter from '@/components/TheFooter.vue'

export default {
  data: () => {
    return {
      mobileView: true,
      showNav: false
    }
  },

  methods: {
    handleView () {
      this.mobileView = window.innerWidth <= 990
    }
  },

  components: {
    InfoBar,
    NavBar,
    NavBarMobile,
    TheFooter
  },

  created () {
    this.handleView()
    window.addEventListener('resize', this.handleView)
  }
}
</script>
