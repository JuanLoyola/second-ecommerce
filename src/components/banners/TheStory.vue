<template>
  <div class="container">
    <div class="img-box">
      <img class="img" src="@/assets/images/story.jpg" alt="img">
    </div>
    <div class="info-box">
      <p class="title">Our Story</p>
      <p class="info">
        “My father is a nutritionist, and I've always been very mindful of what I eat. One that would emphasize prevention, natural medicine, less transformed goods and products that are better for the environment.”
      </p>
      <p class="sign">
        Emna Everard
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheStory'
}
</script>

<style lang="scss" scoped>
.container {
  width: 50%;
  height: 350px;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  background-color: #ebf6f6;
  background-image: url('https://www.kazidomi.com/modules/ab_emna/views/img/bg2.svg');
  .img-box {
    width: 50%;
    height: 100%;
    margin-right: 20px;

    .img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  .info-box {
    width: 50%;
    padding: 0 13px;

    .title {
      width: 50%;
      font-size: 1.5rem;
      font-weight: 600;
      border-bottom: 1px #ccc dashed;
    }

    .info {
      font-weight: 500;
      font-style: italic;
      margin: 20px 0;
      text-align: start;
    }

    .sign {
      display: flex;
      justify-content: flex-end;
      margin-right: 30px;
      font-size: 1.2rem;
      font-weight: 500;
    }
  }
}

@media (max-width: 1300px) {
  .container {
    width: 100%;
    height: 350px;

    .info-box {
      width: 50%;
      padding: 0 13px;

      .title {
        font-size: 1.3rem;
      }

      .info {
        font-size: 0.8rem;
      }

      .sign {
        font-size: 0.8rem;
      }
    }
  }
}
</style>
