<template>
  <form class="form" @submit.prevent>
    <p v-if="msg" class="msg">{{ msg }}</p>
    <strong>Add Post</strong>
    <my-input v-model="post.title" placeholder="Title" />
    <my-input v-model="post.body" placeholder="Text" />
    <my-button class="btn" @click="createPost">Add post</my-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      },
      msg: '',
    };
  },
  methods: {
    createPost() {
      if (this.post.title === '' || this.post.body === '') {
        this.msg = 'Add some text in the form...';
        setTimeout(() => {
          this.msg = '';
        }, 5000);
        return;
      }

      this.post.id = Date.now();

      this.$emit('create', this.post);

      this.post = {
        title: '',
        body: ''
      }
    },
  },
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
}

.msg {
  background: teal;
  color: #fff;
  padding: 15px 60px;
  border-radius: 5px;
  align-self: center;
}

.btn {
  align-self: end;
}
</style>
