<template>
  <div id="navigation-mobile">
    <div class="search">
      <input type="text" placeholder="Search..." />
      <i class="fas fa-search"></i>
    </div>
    <ul>
      <li>Savoury</li>
      <li>Drinks</li>
      <li>Body care</li>
      <li>Home</li>
      <li>Deals</li>
    </ul>
    <div class="social-media">
      <a href="https://www.linkedin.com/in/loyolajuan" target="_blank" rel="noopener noreferrer"><i class="fab fa-linkedin"/></a>
      <a href="https://github.com/JuanLoyola" target="_blank" rel="noopener noreferrer"><i class="fab fa-github"/></a>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
#navigation-mobile {
  padding: 20px 0 0 0;
  background: #d8d6d6;
  height: 100vh;
  ul {
    list-style: none;
    width: 200px;
    padding-left: 40px;
    li {
      color: #333;
      font-size: 2rem;
      font-weight: bold;
      margin-bottom: 20px;
      cursor: pointer;
      &:hover {
        color: #6e6e6e;
        text-decoration: underline;
      }
    }
  }
  .search {
    position: relative;
    width: 240px;
    margin-bottom: 20px;
    padding-left: 20px;
    input {
      border: none;
      outline: none;
      width: 180px;
      padding: 10px 50px 10px 20px;
      margin: 0;
      border-radius: 20px;
      background-color: #efefef;
      font-family: "Segoe UI", Tahoma;
      font-size: 1rem;
    }
    i {
      position: absolute;
      right: 5px;
      top: 10px;
      font-size: 1.6rem;
      color: #aaa;
      cursor: pointer;
    }
  }
  .social-media {
    position: absolute;
    left: 40px;
    bottom: 20px;
    i {
      margin: 0 20px 0 0;
      color: #333;
      font-size: 2rem;
    }
  }
}
</style>
