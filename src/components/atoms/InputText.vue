<template>
  <input :class="$style.input" placeholder="タスクを入力してください" :value="value" @input="onInput" />
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  methods: {
    onInput(event) {
      this.$emit('input', event.target.value);
    }
  }
}
</script>

<style module>
.input {
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  transition: padding 0.3s, font-size 0.3s;  /* 追加: スムーズな遷移 */
}
</style>
