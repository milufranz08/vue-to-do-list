<template>
  <div id="app">
    <form @submit.prevent="addTodo">
      <h3>Vue TO-DO List</h3>
      <label>Enter to-do:</label>
      <input type="text" v-model="item" />
      <button>Submit</button>
    </form>
    <List :list="list" @clicked="deleteTodo"></List>
  </div>
</template>

<script>
import List from "./components/List";
export default {
  name: "app",
  data() {
    return {
      item: "",
      list: []
    };
  },
  components: {
    List
  },
  methods: {
    addTodo() {
      this.list.push(this.item);
      this.item = "";
    },
    deleteTodo(index) {
      this.list = [...this.list.slice(0, index), ...this.list.slice(index + 1)];
    }
  }
};
</script>

<style>
body {
  background-color: #05f8af;
  font-family: "Helvetica", "Arial", sans-serif;
}
#app {
  text-align: center;
}

label {
  padding: 1em;
}

input {
  color: #696969;
  font-size: 1.5em;
  outline: 0;
  background-color: #05f8af;
  border-width: 0 0 2px;
  border-color: black;
  margin-right: 1em;
  width: 300px;
}

button {
  border-color: transparent;
  color: white;
  font-weight: bold;
  padding: 0.8em;
  background-color: black;
  border-radius: 15px;
  text-transform: uppercase;
}

button:hover {
  color: #ff04bd;
}
</style>
