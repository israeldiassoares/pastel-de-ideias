<template>
  <div class="text-area-container">
    <textarea
      :placeholder="placeholder"
      name="product-description"
      id="product"
    ></textarea>
  </div>
</template>

<script>
export default {
  props: {
    placeholder: {
      type: String,
      required: true,
      default: 'Description'
    }
  }
}
</script>

<style></style>
