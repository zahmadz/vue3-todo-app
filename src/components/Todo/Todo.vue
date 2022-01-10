<template>
    <div :class="['todo', todo.color, todo.checked ? 'opacity-40	' : '']">
        <span class="content">{{todo.content}}</span>
        <span class="close" @click="removeTodo(index)">X</span>
    </div>
</template>

<script>
export default {
    props: ['todo', 'todos', 'index'],
    methods: {
        removeTodo(index){
            this.todos.splice(index, 1)
        }
    }
}
</script>

<style>
    .todo {
  @apply flex-1 text-white font-bold rounded shadow-lg cursor-pointer select-none relative flex items-center overflow-hidden
}

.todo .content{
    @apply inline-block text-center flex-1
}

.todo .close{
    @apply inline-block bg-red-400 text-white p-4 z-20
}

.todo.cyan{
  @apply bg-cyan-500 shadow-cyan-500/50
}

.todo.blue{
  @apply bg-blue-500 shadow-blue-500/50
}

.todo.indigo{
  @apply bg-indigo-500 shadow-indigo-500/50
}

.todo.pink{
  @apply bg-pink-500 shadow-pink-500/50
}

.todo.teal{
  @apply bg-teal-500 shadow-teal-500/50
}

.todo.stone{
  @apply bg-stone-500 shadow-stone-500/50
}
</style>