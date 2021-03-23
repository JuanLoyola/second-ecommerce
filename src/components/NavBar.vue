<template>
  <div class="container">
    <div class="search">

      <div class="left">
        <img class="logo" src="@/assets/images/logo.png" alt="Logo">
        <p class="title">Vegan <br> Shop</p>
      </div>

      <div class="search-box">
        <input type="text" placeholder="Search for articles" />
        <i class="fas fa-search"></i>
      </div>

      <div class="right">
        <img class="cart" src="@/assets/images/cart.png" alt="cart">
        <p class="quantity">0</p>
        <span><i id="menu" class="fas fa-bars"></i></span>
      </div>

    </div>

    <div class="menu">
      <div class="items">
        <a href="#" class="link">savoury</a>
        <a href="#" class="link">sweet</a>
        <a href="#" class="link">drinks</a>
        <a href="#" class="link">beauty</a>
        <a href="#" class="link">body care</a>
        <a href="#" class="link">baby</a>
        <a href="#" class="link">health</a>
        <a href="#" class="link">home</a>
        <a href="#" class="link">kazidomi</a>
        <a href="#" class="link">bulk</a>
        <a href="#" class="link">new</a>
        <a href="#" class="link-deals">deals</a>
        <a href="#" class="link-membership">membership</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NavBar'
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: auto;
  background: #fff;
  display: flex;
  flex-flow: column nowrap;
  position: sticky;
  top: 0;
  border-bottom: rgba(51, 51, 51, 0.288) 1px dashed;
  z-index: 3;

  .search {
    width: 65%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-flow: row nowrap;
    margin-top: 20px;

    .left {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-flow: row nowrap;

      .logo {
        width:45px;
        height: 45px;
        margin-right: 25px;
      }

      .title {
        font-weight: 600;
        font-size: 1.3rem;
      }
    }

    .search-box {
      position: relative;
      width: 100%;
      max-width: 400px;
      input {
        border: none;
        outline: none;
        width: calc(100% - 80px);
        padding: 15px 60px 15px 20px;
        margin: 0;
        border-radius: 20px;
        background-color: #efefef;
        font-family: "Segoe UI", Tahoma;
        font-size: 1rem;
      }
      i {
        position: absolute;
        right: 20px;
        top: 15px;
        font-size: 1.6rem;
        color: #aaa;
        cursor: pointer;
      }
    }

    .right {
      width: 90px;
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      flex-flow: row nowrap;

      .cart {
        width: 25px;
      }

      .quantity {
        font-weight: 600;
        color: #bec0c4;
      }
    }
  }

  .menu {
    width:65%;
    margin: 10px 0;

    .items {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-flow: row nowrap;
      list-style: none;
      text-transform: uppercase;
      font-size: 0.8rem;
      font-weight: 600;

      .link {
        color: #333;
      }

      .link:hover {
        color: #00c0bc;
      }

      .link-deals {
        color: #fd7246;
      }

      .link-deals:hover {
        color: #b65639;
      }

      .link-membership {
        width: 130px;
        height: 35px;
        background-color:#00c0bc;
        color: #f1f1f1;
        display: flex;
        justify-content: center;
        align-items: center;
      }

      .link-membership:hover {
        background-color: #0da09d;
      }
    }
  }
}

@media (max-width: 1300px) {
  .container {
    width: 100%;
    height: auto;
    background: #fff;
    display: flex;
    flex-flow: column nowrap;
    position: sticky;
    top: 0;
    border-bottom: rgba(51, 51, 51, 0.288) 1px dashed;

    .search {
      width: 65%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-flow: row nowrap;

      .left {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: row nowrap;

        .logo {
          width:45px;
          height: 45px;
          margin-right: 25px;
        }

        .title {
          font-weight: 600;
          font-size: 1.3rem;
        }
      }

      .center {
        width: 50%;
        height: 40px;
        margin: 0 40px;

        .input {
          width: 100%;
          height: 100%;
        }

        input {
          padding-left: 20px;
        }

        input:focus {
          outline-color: #b6b3b3;
        }

        input::placeholder {
          color: #333;
          font-size: 1rem;
        }
      }

      .right {
        width: 90px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-flow: row nowrap;

        .cart {
          width: 25px;
        }

        .quantity {
          font-weight: 600;
          color: #bec0c4;
        }
      }
    }

    .menu {
      width:65%;
      margin: 10px 0;

      .items {
        display: flex;
        justify-content: space-between;
        align-items: center;
        flex-flow: row nowrap;
        list-style: none;
        text-transform: uppercase;
        font-size: 0.8rem;
        font-weight: 600;

        .link {
          color: #333;
          display: none; // cambiar para ajustar el responsive
        }

        .link:hover {
          color: #00c0bc;
        }

        .link-deals {
          color: #fd7246;
        }

        .link-deals:hover {
          color: #b65639;
        }

        .link-membership {
          width: 130px;
          height: 35px;
          background-color:#00c0bc;
          color: #f1f1f1;
          display: flex;
          justify-content: center;
          align-items: center;
        }

        .link-membership:hover {
          background-color: #0da09d;
        }
      }
    }
  }
}
</style>
