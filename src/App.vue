<template>
  <div id="app">
    <h1>Todo application!!!!!</h1>
    <AddTodo
        @add-todo="addTodo"

    />
    <hr />
    <TodoList :todos="todos"
      @remove-todo="removeTodo"
    />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList"
import  AddTodo from "@/components/AddTodo"
export default {
  name: "App",
  data() {
    return {
      todos: [
        { id: 1, title: "Купить хлеб", completed: false },
        { id: 2, title: "Купить масло", completed: false },
        { id: 3, title: "Купить пиво", completed: false },
      ],
    };
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !==id)
    },
    addTodo(todo) {
      this.todos.push(todo)
    }
  },
  components: {
    TodoList, AddTodo
  },
};
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
</style>