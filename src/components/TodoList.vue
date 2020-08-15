<template>
    <div>
        <ul>
            <TodoItem
            v-for="(todo, i) of todos1"
            v-bind:todo="todo"
            :key="todo.id"
            v-bind:index="i"
            v-on:remove-todo="removeTodo"
            />
        </ul>
    </div>
</template>
<script>
    import TodoItem from '@/components/TodoItem'
    export default {
        props: ['todos1'],
        components: {
            TodoItem
        },
        methods: {
            removeTodo(id) {
                this.$emit('remove-todo',id)
            }
        }
    }
</script>


<style scoped>
    ul{
        list-style: none;
        margin:0;
        padding: 0;
    }
</style>