<template>
  <button :class="$style.button" @click="onClick">{{ label }}</button>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      required: true
    }
  },
  methods: {
    onClick() {
      console.log('buttom clicked');
      this.$emit('click');
    }
  }
}
</script>

<style module>
.button {
  padding: 8px 16px;
  background-color: #007BFF;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
.button:hover {
  background-color: #0056b3;
}
</style>
