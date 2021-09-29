<template>
  <div class="modal" v-if="show" @click="hideModal">
    <div class="modal__content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'MyModal',
    props: {
      show: {
        type: Boolean,
        default: false
      }
    },
    methods: {
      hideModal() {
        this.$emit('update:show', false);
      }
    }
  }
</script>

<style scoped>
  .modal {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    background-color: rgba(0, 0, 0, .5);
  }

  .modal__content {
    min-width: 300px;
    min-height: 50px;
    margin: auto;
    padding: 20px;
    background-color: #fff;
    border-radius: 10px;
  }
</style>
