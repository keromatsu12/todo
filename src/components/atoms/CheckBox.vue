<template>
  <input type="checkbox" :class="$style.checkbox" :checked="checked" @change="onChange" />
</template>

<script>
export default {
  props: {
    checked: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    onChange(event) {
      this.$emit('change', event.target.checked);
    }
  }
}
</script>

<style module>
.checkbox {
  margin-right: 8px;
}
</style>
