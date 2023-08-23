<template>
  <div :class="$style.checkboxContainer">
    <input type="checkbox" :class="$style.checkbox" :checked="checked" @change="onChange" />
    <span :class="$style.customCheckbox"></span>
  </div>
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
.checkboxContainer {
  position: relative;
  display: inline-block;
  width: 20px;
  height: 20px;
}

.checkbox {
  position: absolute;
  opacity: 0;
  width: 20px;
  height: 20px;
  cursor: pointer;
  z-index: 1;
}

.customCheckbox {
  position: absolute;
  top: 0;
  left: 0;
  width: 20px;
  height: 20px;
  background-color: #eee;
  border-radius: 4px;
  transition: background-color 0.3s;
}

.checkbox:checked + .customCheckbox {
  background-color: #2196F3;
}

.customCheckbox::after {
  content: '';
  position: absolute;
  display: none;
}

.checkbox:checked + .customCheckbox::after {
  display: block;
}

.customCheckbox::after {
  left: 7px;
  top: 3px;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}
</style>
