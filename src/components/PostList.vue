<template>
  <div v-if="posts.length > 0">
    <strong>Posts List</strong>
    <post-item
      v-for="post in posts"
      :key="post.id"
      :post="post"
      @remove="$emit('remove', post.id)"
    />
  </div>
  <strong v-else>List of the posts are empty...</strong>
</template>

<script>
import PostItem from '@/components/PostItem';

export default {
  components: { PostItem },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped></style>
