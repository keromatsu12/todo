<template>
  <button :class="$style.button" @click.stop="onClick" :disabled="disabled">
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
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    onClick() {
        this.$emit('clicked');
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
.button:disabled {
  background-color: #b2b2b2;  /* 非活性時の背景色 */
  color: #e0e0e0;  /* 非活性時のテキスト色 */
  cursor: not-allowed;  /* 非活性時のカーソル */
  pointer-events: none;  /* 非活性時のイベントハンドリングを防止 */
}
.icon {
  width: 20px;
  height: 20px;
  margin-right: 8px;
}
</style>
