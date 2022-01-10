<template>
    <div class="formAddTodo">
        <form @submit.prevent="handleAddTodo" class="addTodo">
            <input type="text" class="" placeholder="type new todo here..." ref="newTodo" required>
        </form>
    </div>
</template>

<script>
    export default {
        props: ['Todos'],
        methods: {
            handleAddTodo(){
                const colors = ["cyan", "blue", "indigo", "pink", "teal", "stone"]
                const todo = {
                    id: Math.random(),
                    color: colors[Math.floor(Math.random() * ((colors.length-1) - 0 + 1) + 0)],
                    content: this.$refs.newTodo.value,
                    checked: false
                }

                this.Todos.push(todo)
                this.$refs.newTodo.value = ''
            }
        }
    }
</script>

<style>
    .formAddTodo {
        @apply fixed bottom-0 left-0 right-0 p-4 z-30
    }

    .formAddTodo input {
        @apply w-full py-2 px-6 text-xl font-bold rounded-full focus:outline-0
    }
</style>