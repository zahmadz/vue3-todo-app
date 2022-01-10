<template>
    <div class="todos">
      <Todo v-for="(todo, index) in todos" :index="index" :key="todo.id" :todo="todo" :todos="todos" @click="checkTodo(todo)"/>
    </div>
</template>

<script>
import Todo from './Todo.vue';

export default {
    props: ['todos'],
    components: {
        Todo
    },
    methods: {
        checkTodo(todo){
            todo.checked = !todo.checked
        }
    }
}
</script>

<style>
.todos{
  @apply grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 p-4
}
</style>