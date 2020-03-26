<template>
  <div class="container">
    <div class="header-container">
      <img
        src="../assets/imgs/wave.svg"
        alt=""
        class="header-wave-background"
      />
      <img src="../assets/imgs/logo.svg" alt="" class="header-logo" />
    </div>
    <img
      src="../assets/imgs/pastel-paralax.png"
      alt=""
      class="pastel-image-parallax"
    />
    <img src="../assets/imgs/pasteis-img.png" alt="" class="pastel-image" />
    <div class="main-container">
      <RegisterProduct />
    </div>
  </div>
</template>

<script>
import RegisterProduct from '../components/organisms/RegisterProduct'

export default {
  components: { RegisterProduct },
  data() {
    return {
      dropzoneOptions: {
        url: 'https://httpbin.org/post',
        thumbnailWidth: 150,
        maxFilesize: 0.5,
        headers: { 'My-Awesome-Header': 'header value' },
        dictDefaultMessage:
          '<img src="../assets/icons/upload-icon.png" /> Jogue aqui o arquivo de imagem do seu pastel ou clique para localizar a pasta.'
      }
    }
  }
}
</script>

<style lang="scss">
.container {
  margin: 0;
  padding: 0;
  min-width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background: transparent
    radial-gradient(
      closest-side at 50% 50%,
      #ffffff 0%,
      #ffffff 67%,
      #ffffff00 100%
    )
    0% 0% no-repeat padding-box;
  opacity: 1;

  .pastel-image-parallax {
    position: absolute;
    z-index: 1;
    left: 60px;
  }
  .pastel-image {
    position: absolute;
    right: 355px;
    top: 193px;
  }
  .header-container {
    display: flex;
    flex-direction: column;
  }
  .header-wave-background {
    height: 100%;
    width: 100%;
  }
  .header-logo {
    position: absolute;
    top: 61px;
    left: 522px;
  }
  .main-container {
    width: 1180px;
    position: absolute;
    top: 348px;
    background: #ffffff 0% 0% no-repeat padding-box;
    box-shadow: 0px 0px 30px #740b0b45;
    border-radius: 20px;
    opacity: 1;
    /*
    .register-product {
      &-form {
        position: relative;
        padding: 0 20px 0 20px;

        .form-product {
          &-description {
            margin: 0 0 20px 0;
          }
          &-image {
            margin: 0 0 50px 0;
          }
        }
        .product-description {
          width: 100%;
          height: 80px;
        }
      }
      &-header {
        display: flex;
        justify-content: space-between;
        padding: 25px 20px 0 20px;
        border-radius: 20px 20px 0 0;
        background: #ffca00;
      }
      &-title {
        font-size: 24px;
        color: #a03400;
        font-family: 'Roboto', sans-serif;
        font-weight: bold;
        font-style: italic;
        padding-left: 60px;
      }
      &-footer {
        position: absolute;
        top: 373px;
        left: 373px;
        button {
          width: 200px;
          height: 60px;
          border-radius: 30px;
          opacity: 1;
          text-transform: uppercase;
          text-align: center;
          font-family: 'Roboto', sans-serif;
          font-weight: bold;
          letter-spacing: 0;
          border: none;
          margin: 0 35px 0 0;
        }
        .clear-product {
          background: #e43636;
          color: #fff;
        }
        .register-product {
          background: #ffca00;
          color: #a03400;
        }
      }
    }
    .form-product-info {
      display: flex;
      justify-content: space-between;
      position: relative;
      bottom: 15px;
      z-index: 2;
    }
    */
  }
}
</style>
