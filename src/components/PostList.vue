<template>
  <div v-if="posts.length > 0" class="postList">
    <h2>Posts</h2>
    <Post
      :post="post"
      v-for="post in posts"
      @delete="$emit('delete', post)"
      :key="post.id"
    />
  </div>
  <h2 v-else>Posts List is empty</h2>
</template>

<script>
import Post from './Post.vue'
export default {
  components: { Post },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {}
  },
  methods: {},
}
</script>

<style scoped>
h2 {
  text-align: center;
  margin-bottom: 1rem;
}
</style>
