<template>
  <div :class="$style.todoItem">
    <check-box :checked="todo.done" @checkbox-value-Changed="checkboxValueChanged" />
    <todo-label :text="todo.text"></todo-label>
    <primary-button label="削除" @clicked="removeTodo" :disabled="!todo.done"/>
  </div>
</template>

<script>
import CheckBox from '../atoms/CheckBox.vue';
import PrimaryButton from '../atoms/PrimaryButton.vue';
import TodoLabel from '../atoms/TodoLabel.vue';

export default {
  components: {
    PrimaryButton,
    CheckBox,
    TodoLabel
  },
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    checkboxValueChanged(newDoneValue) {
      this.$emit('update-todo', { ...this.todo, done: newDoneValue });
    },
    removeTodo() {
      this.$emit('remove', this.todo);
    }
  }
}
</script>

<style module>
.todoItem {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 8px 16px;
  background-color: #f9f9f9;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  margin-bottom: 8px;
  transition: background-color 0.3s;
}
</style>

