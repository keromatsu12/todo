<template>
  <normal-template>
      <input-form @add="onAdd" />
      <todo-list :todos="todos" @delete="onDelete" />
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
      console.log("TodoTemplate.vue");
      this.$emit('add', item)
    },
    onDelete(index) {
      this.$emit('delete', index)
    }
  }
}
</script>
