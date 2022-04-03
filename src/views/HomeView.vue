<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="posts.length" :posts="posts" />
    <div v-else>Loading...</div>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import getPosts from "../composables/getPosts";
export default {
  name: "HomeView",
  components: { PostList },
  setup() {
    const { posts, load } = getPosts();
    load();
    return { posts };
  },
};
</script>
