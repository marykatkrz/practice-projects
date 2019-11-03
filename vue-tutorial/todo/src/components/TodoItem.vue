<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
        <input type="checkbox" v-on:change="markComplete">
        {{todo.title}}
        <button @click="$emit('del-todo', todo.is)" class="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props: ["todo"],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    .todo-item{
        background: white;
        padding: 10px;
        border-bottom: 1ps grey dotted;
    }
    .is-complete{
        text-decoration: line-through;
    }
</style>