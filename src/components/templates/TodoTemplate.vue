<template>
  <div>
    <input-form @add="onAdd" />
    <todo-list :todos="todos" @delete="onDelete" />
  </div>
</template>

<script>
import InputForm from '@/components/molucules/InputForm.vue'
import TodoList from '@/components/organisms/TodoList.vue'

export default {
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  components: {
    InputForm,
    TodoList
  },
  methods: {
    onAdd(item) {
      this.$emit('add', item)
    },
    onDelete(index) {
      this.$emit('delete', index)
    }
  }
}
</script>
