<template>
  <div>
    <h3>My Todo</h3>
    <input v-model="newTodo" placeholder="Input here...">
    <button v-on:click="addTodo()">ADD</button>

    <h5>Todo List</h5>
    <ul>
      <li v-for="(todo, i) in todos" v-bind:key="i">
        {{todo}}
        <button v-on:click="deleteTodo(i)">DEL</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      newTodo: ''
    }
  },
  methods: {
    addTodo() {
      if (this.newTodo === '') return;
      this.todos.push(this.newTodo);
      this.newTodo = '';
    },
    deleteTodo(i) {
      this.todos.splice(i, 1);
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
