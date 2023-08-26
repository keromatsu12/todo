<template>
  <table class="todo-table">
    <thead>
      <tr>
        <th>TaskList</th>
      </tr>
    </thead>
    <tbody v-if="areTodosCompleted"> 
      <tr>
        <td class="empty-message">すべてのタスクが完了しました</td>
      </tr>
    </tbody>
    <tbody v-else>
      <tr v-for="todo in todos" :key="todo.id">
        <td><todo-item :todo="todo" @update-todo="updateTodo" @remove="removeTodo" /></td>
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
  computed: {
    areTodosCompleted: {
      get () {
        return this.todos.length === 0
      }
    }
  },
  methods: {
    updateTodo(todo) {
      this.$emit('update-todo', todo);
    },
    removeTodo(todo) {
      this.$emit('remove', todo.id);
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

.empty-message {
  text-align: center;     /* テキストをセンタリング */
  color: #888;            /* グレイッシュな色を指定 */
  font-weight: bold;      /* テキストを太字にする */
  font-style: italic;     /* テキストを斜体にする */
  font-size: 1.1em;       /* フォントサイズを大きくする */
}

</style>

