<template>
  <div class="input-content">
    <input :type="type" :placeholder="placeholder" class="input" />
  </div>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      required: true,
      default: 'text'
    },
    placeholder: {
      type: String,
      required: true,
      default: 'Digite Algo'
    }
  }
}
</script>

<style></style>
