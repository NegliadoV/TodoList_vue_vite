<script setup>
import TodoItem from './components/TodoItem.vue';
import { ref } from 'vue';

const currentDate = ref(new Date().toLocaleDateString())

</script>

<template>
    <div class="todo">
        <div class="header">
            <h1 class="title">Todo List</h1>  
        </div>
        <div class="todo__list">
            <div class="todo__title">Today</div>
            <p class="todo__date">{{currentDate}}</p>
           <todo-item />
        </div>
    </div>
</template>

<style scoped>

</style>
