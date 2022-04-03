<template>
  <div v-if="post" class="post">
    <h3>{{ post.title }} - {{ post.id }}</h3>
    <p class="pre">
      {{ post.body }}
    </p>
  </div>
</template>

<script>
import getPost from "../composables/getPost";
export default {
  props: ["id"],
  setup(props) {
    const { post, load } = getPost(props.id);
    load();
    return { post };
  },
};
</script>

<style>
.post {
  max-width: 600px;
  margin: 0.5rem auto;
  border: 2px solid #444;
  border-radius: 5px;
}
.post p {
  color: #444;
  line-height: 1.5em;
  margin-top: 40px;
}
.post a {
  text-decoration: none;
  color: rgb(16, 230, 105);
}
.post a:hover {
  text-decoration: none;
  color: rgb(19, 218, 52);
}
.pre {
  white-space: pre-wrap;
}
</style>
