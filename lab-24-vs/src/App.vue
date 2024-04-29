<template>
 <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App (HSE-LAB Heftig krasser text)"/>
    <div>
      <table>
        <thead>
          <tr>
            <th>ToDo List</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(todo, index) in todos" :key="index">
            <td>{{ todo }}</td>
          </tr>
        </tbody>
      </table>
      <form @submit.prevent="addTodo">
        <input v-model="newTodo" type="text" placeholder="New ToDo">
        <button type="submit">Add</button>
      </form>
      <button @click="deleteTodo">Delete</button>
    </div>
 </div>
</template>


<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
 name: 'App',
 components: {
    HelloWorld
 },
 data() {
    return {
      todos: ['First ToDo', 'Second ToDo'], // Initial ToDo list
      newTodo: '' // Placeholder for new ToDo input
    }
 },
 methods: {
    addTodo() {
      if (this.newTodo) {
        this.todos.push(this.newTodo);
        this.newTodo = '';
      }
    },
    deleteTodo() {
      if (this.todos.length > 0) {
        this.todos.pop();
      }
    }
 }
}
</script>


<style>
#app {
 font-family: Avenir, Helvetica, Arial, sans-serif;
 -webkit-font-smoothing: antialiased;
 -moz-osx-font-smoothing: grayscale;
 text-align: center;
 color: #2c3e50;
 margin-top: 60px;
}

table {
 width: 100%;
 border-collapse: collapse;
}

th, td {
 border: 1px solid #ddd;
 padding: 8px;
}

th {
 padding-top: 12px;
 padding-bottom: 12px;
 text-align: left;
 background-color: #4CAF50;
 color: white;
}

input[type="text"] {
 width: 100%;
 padding: 12px 20px;
 margin: 8px 0;
 box-sizing: border-box;
}

button {
 background-color: #4CAF50;
 color: white;
 padding: 14px 20px;
 margin: 8px 0;
 border: none;
 cursor: pointer;
 width: 100%;
}

button:hover {
 opacity: 0.8;
}
</style>

