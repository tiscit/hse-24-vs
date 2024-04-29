<template>
  <div id="app">
    <header>
      <img class="logo-hse" alt="Hse logo" src="./assets/hse.svg">
      <h1>Lab - Parallel and Distributed Systems</h1>
    </header>
    <div class="container">
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
      <div class="input-buttons">
        <input v-model="newTodo" type="text" placeholder="New ToDo">
        <button class="add-btn" type="submit" @click="addTodo"><i class="fas fa-plus"></i> Add</button>
        <button class="delete-btn" @click="deleteTodo"><i class="fas fa-trash"></i> Delete</button>
      </div>
    </div>
    <footer>
      <img class="logo-vue" alt="Vue logo" src="./assets/logo.png">
      <p font-size="14">SS24 - Team: Damaris Kröner & Timo Schaller</p>
    </footer>
  </div>
</template>


<script>
export default {
  name: 'App',
  components: {
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
      const index = this.todos.indexOf(this.newTodo);
      if (index > -1) {
          this.todos.splice(index, 1);
          this.newTodo = ''; // Clear the input field after deletion
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
  margin: 60px auto;
  max-width: 800px;
  /* Limit the width of the app */
}

header,
footer {
  background-color: #f8f9fa;
  padding: 20px;
  text-align: center;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: nowrap;
}

header h1 {
  font-size: 25px;
  margin: 0;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 20px;
  background-color: white;
}

th,
td {
  border: 1px solid #ddd;
  padding: 8px;
}

th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #35495e;
  color: white;
}

.input-buttons {
  display: flex;
  justify-content: space-between;
  width: 80%;
  margin-bottom: 20px;
}

input[type="text"] {
  flex-grow: 1;
  padding: 12px 20px;
  margin: 8px 0;
  margin-right: 10px;
  box-sizing: border-box;
}

button {
  background-color: #41b883;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  margin-left: 10px;
  border: none;
  cursor: pointer;
}

button:hover {
  opacity: 0.75;
}

.add-btn {
  background-color: #4caf50;
}

.delete-btn {
  background-color: #a00120;
}

.logo-vue {
  width: 20px;
  height: auto;
  margin-right: 10px;
}

.logo-hse{
  width: 80px;
  height: auto;
  margin-right: 50px;
}
</style>