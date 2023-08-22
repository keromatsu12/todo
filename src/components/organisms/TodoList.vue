<template>
  <table class="todo-table">
    <thead>
      <tr>
        <th>Task</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="todo in todos" :key="todo.id">
        <td><todo-item :todo="todo" @toggle-done="toggleDone" @remove="removeTodo" /></td>
      </tr>
    </tbody>
  </table>
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

<style scoped>
.todo-table {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
}

.todo-table thead {
  background-color: #f7f7f7;
}

.todo-table th, .todo-table td {
  border: 1px solid #e0e0e0;
  padding: 10px 15px;
  text-align: left;
}

.todo-table th {
  font-weight: bold;
}

.todo-table button {
  background-color: #e57373;
  color: #fff;
  border: none;
  padding: 5px 10px;
  border-radius: 3px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.todo-table button:hover {
  background-color: #ef5350;
}
</style>

