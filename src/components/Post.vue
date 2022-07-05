<template>
  <div class="post">
    <strong>Название: </strong>{{ post.title }}
    <strong>Описание: </strong>{{ post.body }}
    <MyButton @click="deleteEvent">delete</MyButton>
  </div>
</template>

<script>

export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {}
  },
  methods: {
    deleteEvent() {
      this.$emit('delete', this.post)
    }
  }
}
</script>

<style scoped>
.post {
  border: 2px solid teal;
  margin-bottom: 1rem;
  font-size: 1.2rem;
  padding: 0.5rem;
  display: flex;
  align-items: center;
  gap: 1rem;
}
button {
  margin-left: auto;
}
</style>
