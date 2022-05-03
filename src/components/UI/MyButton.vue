<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "my-button"
};
</script>

<style scoped>
.btn {
  padding: 10px 15px;
  border: none;
  outline: none;
}
</style>