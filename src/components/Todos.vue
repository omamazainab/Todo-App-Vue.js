<template>
  <div>
    <ul>
      
        <TodoItem
          v-for="todo in todos"
          :key="todo.id"
          :title="todo.title"
          :completed="todo.completed"
          @on-toggle="toggleTodo(todo)"
        />
      
    </ul>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  components: {
    TodoItem,
  },

  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Go workout",
          completed: true,
        },
        {
          id: 2,
          title: "Do laundry",
          completed: false,
        },
        {
          id: 3,
          title: "Cook food",
          completed: false,
        },
        {
          id: 4,
          title: "Clean up room",
          completed: false,
        },
        {
          i: 5,
          title: "Finish work",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    toggleTodo(todo) {
      todo.completed = !todo.completed;
    },
  },
};
</script>

<style>
</style>