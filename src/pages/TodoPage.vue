<template>
  <todo-template :todos="todos" @add="addItem" @delete="deleteItem" />
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
      },{
        id: 2,
        text: "サンプルタスク2",
        done: false
      }]
    }
  },
  components: {
    TodoTemplate,
  },
    methods: {
    addItem(item) {
      console.log(item);
      if (this.item === '' || undefined) return;

      console.log("TodoPage.vue");
      const newTodo= {
        text: item,
        done: false
      };

      this.todos.push(newTodo);
      // this.newTodoItem = '';
    },
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }

}
</script>
