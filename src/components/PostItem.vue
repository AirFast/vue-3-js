<template>
  <div class="post">
    <div>
      <div><b>Title:</b> {{ post.title }}</div>
    <div><b>Text:</b> {{ post.body }}</div>
    </div>
    <div>
      <my-button @click="$emit('remove', post.id)">Delete</my-button>
    </div>
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
};
</script>

<style scoped>
.post {
  display: flex;
  margin-top: 60px;
  padding: 40px;
  border: 2px solid teal;
  justify-content: space-between;
  align-items: center;
}
</style>
