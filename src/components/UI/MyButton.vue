<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button'
};
</script>

<style scoped>
.btn {
  border: 2px solid transparent;
  border-radius: 5px;
  background: teal;
  color: #fff;
  padding: 13px 30px 10px;
  text-transform: uppercase;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.25s ease-in-out;
}

.btn:hover {
  background: transparent;
  color: teal;
  border: 2px solid teal;
}
</style>
