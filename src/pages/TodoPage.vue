<template>
  <todo-template :todos="todos" @add="addItem" @delete="deleteItem" @update="updateItem"/>
</template>

<script>
import TodoTemplate from '@/components/templates/TodoTemplate.vue';

export default {
   data() {
    return {
      todos : [{
        id: 1,
        text: "サンプルタスク",
        done: false
      }]
    }
  },
  components: {
    TodoTemplate,
  },
    methods: {
    addItem(item) {
      if (item === '' ) {
        alert('入力欄は必須入力です。');
        return;
      }

      const maxId = this.todos.length > 0 ? 
        Math.max(...this.todos.map(t => t.id)) : 0;

      const newTodo = {
        id: maxId + 1, 
        text: item,
        done: false
      };

      this.todos.push(newTodo);
    },
    deleteItem(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    updateItem(updatedTodo){
      const index = this.todos.findIndex(t => t.id === updatedTodo.id);
      this.todos.splice(index, 1, updatedTodo);
    }
  }
}
</script>
