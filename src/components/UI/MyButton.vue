<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'MyButton'
  }
</script>

<style scoped>
.btn {
  padding: 0.5rem 1rem;
  border: 2px solid teal;
  cursor: pointer;
}
</style>