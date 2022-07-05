<template>
  <div class="backdrop" v-if="show" @click="hideModal">
    <div class="modal" @click.stop>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyModal',
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    hideModal() {
      this.$emit('update:show', false)
    }
  }
}
</script>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
}
.modal {
  /* position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%); */
  margin: auto;
  min-height: 200px;
  min-width: 400px;
  background-color: white;
  border-radius: 1rem;
  padding: 1rem;
}
</style>
