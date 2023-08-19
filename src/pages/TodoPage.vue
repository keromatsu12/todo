<template>
  <todo-header />
  <todo-template :todos="todos" @add="addItem" @delete="deleteItem" />
</template>

<script>
import TodoHeader from '@/components/organisms/TodoHeader.vue';
import TodoTemplate from '@/components/templates/TodoTemplate.vue';


export default {
   data() {
    return {
      todos : [{
        text: "サンプルタスク",
        done: false
      },{
        text: "サンプルタスク2",
        done: false
      }]
    }
  },
  components: {
    TodoTemplate,
    TodoHeader,
  },
    methods: {
    addTodo() {
      if (this.newTodoItem.trim() === '') return;

      const newTodo= {
        id: this.nextId,
        item: this.newTodoItem,
        isDone: false
      };

      this.todos.push(newTodo);
      this.newTodoItem = '';
      this.nextId++;
    },
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }

}
</script>
