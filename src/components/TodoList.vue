<template>
  <div>
    <div class='ui centered card'>
      <p>Completed Tasks: {{ todos.filter(todo => {return todo.done === true}).length}}</p>
      <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    </div>
    <todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo" v-on:complete-todo="completeTodo(todo)" />
  </div>
</template>

<script>
import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo,
  },
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    completeTodo(todo) {
      console.log("h")
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
