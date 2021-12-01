<template>
  <div class="container">
    <my-dialog :show="true">
      <post-form @create="createPost"/>
    </my-dialog>
    <post-list :posts="posts" @remove="removePost"/>
  </div>
</template>

<script>
import PostForm from '@/components/PostForm'
import PostList from '@/components/PostList'

export default {
  components: {
    PostForm,
    PostList
  },
  data() {
    return {
      posts: [
        { id: 1, title: 'JavaScript', body: 'Description JavaScript' },
        { id: 2, title: 'React.js', body: 'Description React.js' },
        { id: 3, title: 'Vue.js', body: 'Description Vue.js' },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
    removePost(id) {
      this.posts = this.posts.filter(post => id !== post.id)
    }
  },
};
</script>

<style>
* {
  font-family: sans-serif;
  line-height: 1.7;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  width: 1200px;
  margin: 40px auto;
}
</style>
