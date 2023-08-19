<template>
  <todo-page :todos="todos" />
</template>

<script>
import TodoPage from '@/pages/TodoPage.vue';

export default {
  name: 'App',
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
    TodoPage
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
