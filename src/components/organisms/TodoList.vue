<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      <todo-item :todo="todo" @toggle-done="toggleDone" @remove="removeTodo" />
    </div>
  </div>
</template>

<script>
import TodoItem from '@/components/molucules/TodoItem.vue';

export default {
  components: {
    TodoItem
  },
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  methods: {
    toggleDone(todo) {
      this.$emit('toggle-done', todo);
    },
    removeTodo(todo) {
      this.$emit('remove', todo);
    }
  }
}
</script>
