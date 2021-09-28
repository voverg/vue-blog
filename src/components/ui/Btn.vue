<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'Btn'
  }
</script>

<style scoped>
  .btn {
    padding: 5px;
    border: 1px solid var(--blue);
    border-radius: 3px;
    cursor: pointer;
    transition: all.2s ease-out;
    background-color: transparent;
    font-size: 12px;
  }
  button:hover {
    background-color: var(--blue);
    color: #fff;
  }
</style>
