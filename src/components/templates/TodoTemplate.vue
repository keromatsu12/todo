<template>
  <normal-template>
      <input-form @add="onAdd" />
      <todo-list :todos="todos" @remove="onDelete" @update-todo="onUpdate"/>
  </normal-template>
</template>

<script>
import InputForm from '@/components/molucules/InputForm.vue'
import TodoList from '@/components/organisms/TodoList.vue'
import NormalTemplate from '@/components/templates/NormalTemplate.vue'

export default {
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  components: {
    InputForm,
    TodoList,
    NormalTemplate
  },
  methods: {
    onAdd(item) {
      this.$emit('add', item)
    },
    onDelete(id) {
      this.$emit('delete', id)
    },
    onUpdate(todo) {
      this.$emit('update', todo)
    }
  }
}
</script>
