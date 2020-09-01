<template>
  <div >
      <ul>
          <li v-bind:key="todo.id" v-for="todo in todos">
        <TodoItem v-bind:todo="todo" />
      </li>
      </ul>
      
  </div>
</template>

<script>

import TodoItem from './TodoItem'

export default {
    name: 'Todos',
    components : {
        TodoItem
    },
    props: [
        'todos'
    ]
}
</script>

<style>

</style>