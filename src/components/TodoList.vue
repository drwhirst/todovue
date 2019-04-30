<template>
  <div>
    <p>Completed Tasks: {{ todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <todo v-for="todo in todos" v-bind:todo="todo"/>
  </div>
</template>

<script>
import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
