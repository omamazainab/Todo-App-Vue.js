<template>
  <div class="text-center todo-app">
    <h1>Todo App</h1>
    <ul class="todo-list">
      <AddTodo @on-new-todo="addTodo($event)" />
      <TodoItem
        v-for="(todo,index) in todos"
        :key="index"
        :title="todo.title"
        :completed="todo.completed"
        @on-toggle="toggleTodo(todo)"
        @on-delete="deleteTodo(todo)"
        @on-edit="editTodo(todo,$event)"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";
import AddTodo from "./AddTodo";

export default {
  name: "Todos",
  components: {
    TodoItem,
    AddTodo,
  },

  data() {
    return {
      todos: [
        {
          title: "Go workout",
          completed: true,
        },
        {
          title: "Do laundry",
          completed: false,
        },
        {
          title: "Cook food",
          completed: false,
        },
        {
          title: "Clean up room",
          completed: false,
        },
        {
          title: "Finish work",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo);
    },
    toggleTodo(todo) {
      todo.completed = !todo.completed;
    },
    deleteTodo(deletedTodo) {
      this.todos = this.todos.filter((todo) => todo !== deletedTodo);
    },
    editTodo(todo, title) {
      todo.title = title;
    },
  },
};
</script>

<style scoped>
.todo-app {
  background: #fff;
  margin: 130px 0 40px 0;
  position: relative;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2), 0 25px 50px 0 rgba(0, 0, 0, 0.1);
}
.todo-app > h1 {
  position: absolute;
  top: -70px;
  width: 100%;
  font-size: 100px;
  font-weight: 100;
  text-align: center;
  color: rgba(175, 47, 47, 0.15);
  text-rendering: optimizeLegibility;
  font-family: "roboto";
}
.todo-list {
  margin: 0;
  padding: 0;
  list-style: none;
}
.todo-app::before{
    
    content: '';
    position: absolute;
    right: 0;
    bottom: 0;
    left: 0;
    height: 50px;
    overflow: hidden;
    box-shadow: 0 1px 1px rgba(0, 0, 0, 0.2), 0 8px 0 -3px #f6f6f6, 0 9px 1px -3px rgba(0, 0, 0, 0.2), 0 16px 0 -6px #f6f6f6, 0 17px 2px -6px rgba(0, 0, 0, 0.2);
}
</style>