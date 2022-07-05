<template>
  <div class="app">
    <h1>Blog</h1>
    <div class="btns" @click="showModal">
      <MyButton @click="showModal">Create post</MyButton>
    </div>
    <MyModal v-model:show="isModal">
      <PostForm @create="createPost" />
    </MyModal>
    <PostList :posts="posts" @delete="deletePost" />
  </div>
</template>

<script>
import PostList from './components/PostList.vue'
import PostForm from './components/PostForm.vue'
import MyModal from './components/UI/MyModal.vue'
import MyButton from './components/UI/MyButton.vue'
export default {
  components: { PostList, PostForm, MyModal, MyButton },
  data() {
    return {
      posts: [
        { id: 1, title: 'JavaScript', body: 'Описание 1' },
        { id: 2, title: 'TypeScript', body: 'Описание 2' },
        { id: 3, title: 'Python', body: 'Описание 3' },
      ],
      isModal: false
    }
  },
  methods: {
    createPost(title, body) {
      const newPost = {
        id: Date.now(),
        title,
        body,
      }
      this.posts.push(newPost)
      this.isModal = false
    },
    deletePost(post) {
      // const index = this.posts.findIndex(item => item.id === post.id)
      // this.posts.splice(index, 1)
      this.posts = this.posts.filter((item) => item.id !== post.id)
    },
    showModal() {
      this.isModal = true
    }
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 1rem;
}
h1 {
  margin-bottom: 1rem;
  text-align: center;
}
</style>
