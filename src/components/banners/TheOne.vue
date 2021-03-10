<template>
  <div class="container">
    <div class="card">
      <div class="card-info">
        <h2 class="title">Healthy living has never been so easy</h2>
        <hr class="line">
        <p class="subtitle">Save <span class="discount">up to 50%</span> on your favourite <span class="type"> healthy and organic</span> products delivered to your doorstep!</p>

        <a href="#" class="button">Learn More</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheOne'
}
</script>

<style lang="scss" scoped>
.container {
  background-image: url('../../assets/images/bannerOne.jpg');
  background-size: cover;
  background-position-y: center;
  width: 100%;
  height: 600px;
  display: flex;
  justify-content: flex-start;
  align-items: center;

  .card {
    background-color: #fff;
    width: 450px;
    height: 450px;
    margin-left: 60px;
    -webkit-box-shadow: 2px 4px 5px 0px rgba(143,135,143,1);
    -moz-box-shadow: 2px 4px 5px 0px rgba(143,135,143,1);
    box-shadow: 2px 4px 10px 0px rgba(143,135,143,1);

    &-info {
      padding: 40px;
      display: flex;
      flex-flow: column nowrap;
      justify-content: flex-end;
      align-items: flex-start;
      text-align: start;

      .title {
        font-size: 2.9rem;
        letter-spacing: 2px;
        width: 400px;
      }

      .line {
        border-top: 1px dashed  #b3b2b2;
        width: 100%;
        margin: 20px 0;
      }

      .subtitle {
        font-size: 1.3rem;
        font-weight: 600;

        .discount {
          color: #01b3b0;
        }

        .type {
          color:#fd6d3f;
        }
      }

      .button {
        width: 100%;
        height: 50px;
        background:#00c0bc;
        border-radius: 5px;
        margin: 20px 0;
        display: flex;
        justify-content: center;
        align-items: center;
        color: #f1f1f1;
        font-weight: 500;
        text-decoration: none;
      }

      .button:hover {
        background:#01b3b0;
      }
    }
  }
}

@media (max-width: 1300px) {
  .container {
    width: 100%;
    height: 600px;
    background-position-x: center;
    align-items: flex-start;

    .card {
      background-color: #fff;
      width: 100%;
      height: 270px;
      margin-left: 0px;

      &-info {
        padding: 20px;
        .title {
          font-size: 1.5rem;
          width: 300px;
        }

        .subtitle {
          font-size: 1rem;
        }
      }
    }
  }
}
</style>
