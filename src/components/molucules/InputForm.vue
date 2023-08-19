<template>
  <div :class="$style.inputForm">
    <form @submit.prevent>
      <input-text />
      <primary-button label="追加" @click="addTodo" />
    </form>
  </div>
</template>

<script>
import InputText from '../atoms/InputText.vue';
import PrimaryButton from '../atoms/PrimaryButton.vue';

export default {
  components: {
    PrimaryButton,
    InputText
  },
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    addTodo() {
      this.$emit('add', this.todo);
    }
  }
}
</script>

<style module>
.inputForm {
  display: flex;
  align-items: center;
  gap: 8px; /* input-text と primary-button の間のスペース */
  padding: 8px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  background-color: #f9f9f9;
  transition: background-color 0.3s;
}

.inputForm:hover {
  background-color: #f5f5f5;
}
</style>