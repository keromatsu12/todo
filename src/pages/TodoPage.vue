<template>
  <todo-header />
  <todo-template :todos="todos" @add="addItem" @delete="deleteItem" />
</template>

<script>
import TodoHeader from '@/components/organisms/TodoHeader.vue';
import TodoTemplate from '@/components/templates/TodoTemplate.vue';
import { Todo } from '@types/TodoType';


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

      const newTodo: Todo = {
        id: this.nextId,
        item: this.newTodoItem,
        isDone: false
      };

      this.todos.push(newTodo);
      this.newTodoItem = '';
      this.nextId++;
    },
    deleteTodo(id: number) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }

}
</script>
