<template>
  <button :class="$style.button" @click="onClick">
    <img v-if="iconSrc" :src="iconSrc" :class="$style.icon" alt="Button icon" />
    {{ label }}
  </button>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      required: true
    },
    iconSrc: {
      type: String,
      default: null
    }
  },
  methods: {
    onClick() {
      console.log('button clicked');
      this.$emit('click');
    }
  }
}
</script>

<style module>
.button {
  display: inline-flex;
  align-items: center;
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
.icon {
  width: 20px;
  height: 20px;
  margin-right: 8px;
}
</style>
