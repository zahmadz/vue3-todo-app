<script>
import Todos from './components/Todo/Todos.vue';
import FormAddTodo from './components/Todo/FormAddTodo.vue';

export default {
  data(){
    return{
      todos: [],
    }
  },
  components: {
    Todos,
    FormAddTodo
  }
}
</script>

<template>
  <div class="container mx-auto">
      <Todos :todos="todos" />
      <div class="py-8"></div>
      <FormAddTodo :Todos="todos" />
  </div>
</template>

<style>
.container{
  background: #000034;
  min-height: 100vh;
   max-width: 100% !important;
}
</style>
