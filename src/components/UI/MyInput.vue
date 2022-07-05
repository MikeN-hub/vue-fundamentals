<template>
  <input class="input" type="text" :value="modelValue" @input="updateInput">
</template>

<script>
  export default {
    name: 'MyInput',
    props: {
      modelValue: [String, Number]
    },
    methods: {
      updateInput(e) {
        this.$emit('update:modelValue', e.target.value)
      }
    }
  }
</script>

<style scoped>
.input {
  padding: 0.5rem;
  border: 2px solid teal;
  outline: none;
}
</style>