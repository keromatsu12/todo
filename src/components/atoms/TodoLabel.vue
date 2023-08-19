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
  background-color: #f5f5f5;
  border-radius: 4px;
  font-weight: 500;
  color: #333;
  border: 1px solid #e0e0e0;
}
</style>
