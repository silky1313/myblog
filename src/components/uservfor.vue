<script setup>
import { ref } from 'vue';

// 给每个 todo 对象一个唯一的 id
let id = 0;

const newTodo = ref('');
const todos = ref([
  { id: id++, text: 'Learn HTML' },
  { id: id++, text: 'Learn JavaScript' },
  { id: id++, text: 'Learn Vue' }
]);

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value });
  // 形成的是双向绑定
  newTodo.value = '';
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => {
    return t.id !== todo;
  });
}
</script>

<template>
  <!-- 提交事件将不再重新加载页面 -->
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" />
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo.id)">X</button>
    </li>
  </ul>
</template>