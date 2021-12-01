<template>
  <div class="dialog" v-if="show">
    <div class="dialog-content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'my-dialog',
  props: {
    show: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.dialog {
  position: fixed;
  display: flex;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  background: rgba(255, 255, 255, .8);
}

.dialog-content {
  margin: auto;
  padding: 50px 80px;
  width: 700px;
  min-width: 320px;
  background: #fff;
  border: 1px solid #eee;
  border-radius: 10px;
}
</style>