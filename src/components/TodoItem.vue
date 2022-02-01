<template>
    <div id="todoItem" class="todo">
        <template>
            <div class="todo-body" v-bind:class="{completed: todo.completed}">
                <input
                type="checkbox"
                v-bind:checked="todo.completed? 'checked': ''" v-on:change="checkTodo"
                >
                {{todo.title}}
            </div>
            <div class="todo-actions">
                <v-btn
                red
                @click="$emit('delete-todo', todo.id)"
                >Eliminar</v-btn>
            </div>
        </template>
    </div>
</template>

<script>
export default {
    name: 'TodoItem',
    props: ['todo'],
    methods: {
        checkTodo() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
</style>