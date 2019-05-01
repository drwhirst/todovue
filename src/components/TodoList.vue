<template>
  <div>
    </br>
    <div class='ui centered card'>
      <div class='content'>
      <div class='header'>
          <p>Completed Tasks: {{ todos.filter(todo => {return todo.done === true}).length}}</p>
        </div>
        <div class='header'>
          <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
        </div>
      </div>
    </div>
    <todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo" v-on:complete-todo="completeTodo(todo)" v-on:reverse-todo='reverseTodo(todo)' />
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
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    },
    reverseTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
