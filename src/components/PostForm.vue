<template>
  <form @submit.prevent>
    <h2>Create post</h2>
    <MyInput type="text" placeholder="Название" v-model="post.title" />
    <MyInput type="text" placeholder="Описание" v-model="post.body" />
    <MyButton @click="createPost">add post</MyButton>
  </form>
</template>

<script>
import MyInput from './UI/MyInput.vue'
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      },
    }
  },
  methods: {
    createPost() {
      if(this.post.title.length > 0 & this.post.body.length > 0)
      this.$emit('create', this.post.title, this.post.body)
      this.post = {
        title: '',
        body: '',
      }
    },
  },
  components: { MyInput },
}
</script>

<style scoped>
h2 {
  text-align: center;
  margin-bottom: 1rem;
}
form {
  margin-bottom: 2rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
button {
  align-self: flex-end;
}
</style>
