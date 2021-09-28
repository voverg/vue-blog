<template>
  <input
    type="text"
    class="input"
    :value="modelValue"
    @input="updateValue">
</template>

<script>
  export default {
    name: 'my-input',
    props: {
      modelValue: [String, Number]
    },
    methods: {
      updateValue(event) {
        this.$emit('update:modelValue', event.target.value);
      }
    }
  }
</script>

<style scoped>
  .input {
    min-width: 97%;
    max-width: 100%;
    margin-bottom: 10px;
    padding: 10px;
    border: 1px solid var(--blue);
    border-radius: 3px;
  }
</style>
