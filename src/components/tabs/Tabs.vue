<template>
  <div>
    <p class="title">Our quality standards</p>
    <ul class="nav nav-tabs">
      <li v-for="tab in tabs" :key="tab" class="nav-item">
        <a class="nav-link" :class="{ active: tab === selected }" @click="setTab(tab)"
        >{{ tab }}</a>
      </li>
    </ul>
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    /* Holds all of the tabs data */
    tabs: {
      type: Array,
      required: true
    },
    selected: {
      type: String,
      required: true
    }
  },
  methods: {
    setTab (tab) {
      this.$emit('selected', tab)
    }
  }
}
</script>

<style lang="scss" scoped>
.title {
  font-size: 1.8rem;
  font-weight: 600;
  border-bottom: 1px solid #333;
  margin-top: 30px;
}

.nav {
  margin: 30px 0;
  display: flex;
}

.nav-item {
  margin-right: 40px;
  display: flex;
  padding: 0;
  cursor: pointer;
  font-size: 1.2rem;
  font-weight: 500;

  &:hover {
    color:#23adad;
  }
}

.active {
  color:#23adad;
}
</style>
