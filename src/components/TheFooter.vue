<template>
  <footer class="footer">
    <div class="column">
      <p class="column__sign">
        &copy; Vegan Shop {{currentYear}} All rights reserved
      </p>
    </div>

    <div class="column">
      <p class="column__title">Vegan shop</p>
      <a href="#" class="column__option">Register</a>
      <a href="#" class="column__option">Login</a>
    </div>

    <div class="column">
      <p class="column__title">Help</p>
      <a href="#" class="column__option">Terms & conditions</a>
      <a href="#" class="column__option">Delivery & returns</a>
      <a href="#" class="column__option">Privacy policy</a>
      <a href="#" class="column__option">Help center</a>
    </div>

    <div class="column">
      <p class="column__title">Contacts</p>
      <a href="#" class="column__option">Contact & support</a>
      <a href="#" class="column__option">Conntact for brands</a>
      <a href="#" class="column__option">Vegan shares</a>
      <a href="#" class="column__option">Join us</a>
    </div>

    <div class="column">
      <p class="column__title">Newsletter</p>
      <a class="column__option">Sign up to get all our news, tips and exclusive offers!</a>
      <div class="column__option search-box">
        <input type="text" placeholder="Enter your e-mail" />
        <i class="fas fa-chevron-right"></i>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'TheFooter',

  computed: {
    currentYear () {
      return new Date().getFullYear()
    }
  }
}
</script>

<style lang="scss" scoped>
.footer{
  width: 100%;
  height: 304px;
  background-color: #3c4b5c;
  display: flex;
  flex-flow: row nowrap;
  justify-content: center;
  margin: 0;
  padding: 0;
  font-size: 1rem;

  .column {
    margin-top: 48px;
    width: 296px;
    height: 216px;
    display: flex;
    flex-flow: column nowrap;
    align-items: flex-start;

    &__sign {
      width: 136px;
      text-transform: uppercase;
      color: #f1f1f1;
    }

    &__title {
      margin: 0 0 40px 0;
      color: #f1f1f1;
      text-transform: uppercase;
    }

    &__option {
      color: #959ea7;
      margin-bottom: 8px;
      cursor: pointer;
    }

    &__option:hover {
      color: #90acc9;
    }

    &__social {
      margin-top: 40px;
      display:flex;
      flex-direction: row;

      .icon {
        margin-right: 8px;
      }
    }

    &:nth-child(1) {
      justify-content: space-between;
    }

    .search-box {
      position: relative;
      width: 100%;
      max-width: 400px;
      input {
        border: 1px solid #959ea7;
        outline: none;
        width: calc(100% - 80px);
        height: 35px;
        padding: 15px 60px 15px 20px;
        margin: 0;
        background-color: #3c4b5c;
        font-family: "Segoe UI", Tahoma;
        font-size: 1rem;
        color: #f1f1f1;
      }
      i {
        width: 35px;
        height: 35px;
        position: absolute;
        right: 40px;
        top: 0px;
        font-size: 1.6rem;
        color: #fff;
        cursor: pointer;
        background: #b4dfde;
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }
  }
}

@media (max-width: 1300px) {
  .footer{
    height: 100%;
    flex-flow: column nowrap;
    justify-content: center;
    align-items: center;
    font-size: 1rem;

    .column {
      height: 170px;
      flex-flow: column nowrap;
      align-items: center;

      &__title {
        margin: 0 0 20px 0;
      }
    }
  }
}
</style>
