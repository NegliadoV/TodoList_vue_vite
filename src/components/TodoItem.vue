<script setup>

import {ref} from 'vue'

const todo = ref('')
const tasks = ref([])

const addTodo = () => {
    if (todo.value.trim() !== '') {
        tasks.value.push({text: todo.value, completed: false})
        todo.value = ''
    }   
}

const removeTodo = (i) => {
  tasks.value.splice(i, 1)
}


</script>

<template>
  <div v-for="(task, i) in tasks" :key="i" class="todo__item">
    <label class="checkbox">
        <input @click="" type="checkbox" class="checkbox__input" v-model="task.completed">
       <img v-if="task.completed"  src="../assets/img/check.svg" alt="#">
       <img v-else src="../assets/img/checkOn.svg" alt="#">
       <p :class="{'cross__out': task.completed}" class="todo__text">{{task.text}}</p>
      
    </label>
   
  <button @click="removeTodo" class="remove__todo"><img class="remove__todo_img" src="../assets/img/close.svg" alt="#"></button>
  
  </div>
  <div class="add__todo">
    <input placeholder="Push" @keyup.enter="addTodo" v-model="todo" class="input__todo" type="text">
    <button @click="addTodo" class="btn">
        <img class="plus__img" src="../assets/img/plus.svg" alt="#">
        </button>
    </div>
</template>

<style scoped>

</style>
