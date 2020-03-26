<template>
  <div class="register-product-form">
    <div class="register-product-header">
      <p class="register-product-title">
        Monte aqui o seu cardápio. O que está esperando ?
      </p>
      <!-- toggle -->
      <div class="toggle-food-or-drink">
        <p class="check-food">Comida</p>
        <ToggleButton
          :value="true"
          :color="{
            checked: '#fff',
            unchecked: '#fff'
          }"
          :width="42"
          :height="12"
          class="toggle-option"
        />
        <p class="check-drink">Bebida</p>
      </div>
    </div>
    <div class="register-product-form">
      <div class="form-product-info">
        <Input
          type="text"
          placeholder="Título do Pedido"
          class="product-title "
        />
        <Input type="text" placeholder="Sabor" class="product-flavor" />
        <Input type="number" class="product-price" placeholder="R$" />
      </div>
      <div class="form-product-description">
        <TextArea placeholder="Descrição" class="product-description" />
      </div>
      <div class="form-product-image">
        <!-- Componente drag and drop imagem -->
        <DragDropZone
          id="dropzone"
          ref="myVueDropzone"
          :options="dropzoneOptions"
          class="product-image"
        ></DragDropZone>
      </div>
    </div>
    <div class="register-product-footer">
      <button class="clear-product">
        Limpar
      </button>
      <button class="register-product">
        Cadastrar
      </button>
    </div>
  </div>
</template>

<script>
import DragDropZone from 'vue2-dropzone'
import 'vue2-dropzone/dist/vue2Dropzone.min.css'
import { ToggleButton } from 'vue-js-toggle-button'
import Input from '../molecules/Input'
import TextArea from '../molecules/TextArea'

export default {
  components: {
    Input,
    TextArea,
    DragDropZone,
    ToggleButton
  },
  data() {
    return {
      dropzoneOptions: {
        url: 'https://httpbin.org/post',
        thumbnailWidth: 100,
        maxFilesize: 0.5,
        dictDefaultMessage:
          "<i class='upload-icon'> </i>Jogue aqui o arquivo de imagem do seu pastel ou clique para localizar a pasta."
      }
    }
  }
}
</script>

<style lang="scss">
.register-product-form {
  ::-webkit-input-placeholder {
    /* Chrome/Opera/Safari */
    color: #a03400;
    font-size: 16px;
    font-family: 'Robot', sans-serif;
    text-align: left;
    letter-spacing: 0;
    opacity: 1;
    vertical-align: top;
    padding: 9px 0 9px 0;
  }
  .register-product {
    &-form {
      position: relative;
      padding: 0 20px 0 20px;
      input,
      textarea {
        border: none;
        border-radius: 10px;
        border: 1px solid #e43636;
        resize: none;
        padding: 0 20px;
        &::-webkit-outer-spin-button,
        &::-webkit-inner-spin-button {
          -webkit-appearance: none;
          margin: 0;
        }

        /* Firefox */
        &[type='number'] {
          -moz-appearance: textfield;
        }
      }
      .form-product {
        &-description {
          margin: 0 0 20px 0;
        }

        &-image {
          margin: 0 0 50px 0;
          border-color: green;
          & .vue-dropzone {
            background: #ffffff;
            border: 1px solid #e43636;
            border-radius: 10px;
            opacity: 1;
            text-align: center;
            font-family: 'Roboto' sans-serif;
            letter-spacing: 0;
            color: #a03400;
            opacity: 1;
            padding: 0;
          }
          .upload-icon {
            background-image: url('../../assets/icons/upload.svg');
            background-repeat: no-repeat, repeat;
            height: 45px;
            width: 48px;
            background-size: contain;
            margin: 0 46% 5px;
            display: block;
          }
        }
      }
      .product-description textarea {
        width: 100%;
        height: 80px;
      }
    }
    &-header {
      display: flex;
      justify-content: space-between;
      padding: 25px 20px 16px 20px;
      border-radius: 20px 20px 0 0;
      background: #ffca00;

      .toggle-food-or-drink {
        display: flex;
        align-items: baseline;
        & p {
          font-family: 'Roboto', sans-serif;
          font-size: 16px;
          letter-spacing: 0;
          color: #a03400;
          opacity: 1;
          padding: 0 10px 0 10px;
        }
        & .v-switch-button {
          background-color: #e33535;
          padding: 10px;
          top: -7px;
          left: -5px;
        }
      }
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
      position: relative;
      top: 24px;
      left: 0;
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

    .product {
      &-title input {
        width: 460px;
        height: 40px;
      }
      &-flavor input {
        width: 480px;
        height: 40px;
      }
      &-price input {
        width: 160px;
        height: 40px;
      }
    }
  }
}
</style>
