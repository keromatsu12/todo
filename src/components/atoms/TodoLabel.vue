<template>
  <span :class="$style.label">{{ text }}</span>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: true
    }
  }
}
</script>

<style module>
.label {
  display: inline-block;
  padding: 4px 8px;
  background-color: #928e8e;
  border-radius: 4px;
  font-weight: 750;
  color: #333;
  border: none;
}
</style>
