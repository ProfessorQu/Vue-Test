<template>
  <div id="app">
    <input v-model="newTodoText" @keyup.enter="addTodo">
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        <span>{{ todo.text }}</span>
        <button @click="removeTodo(todo)">X</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      newTodoText: '',
      todos: [
        { text: "Add some todos" }
      ]
    }
  },

  methods: {
    addTodo() {
      var text = this.newTodoText.trim()
      console.log(this.newTodoText)
      if (text) {
        this.todos.unshift({
          text: text
        })
        this.newTodoText = ''
      }
    },

    removeTodo(todo) {
      this.todos.splice(this.todos.indexOf(todo), 1)
    }

  }
}
</script>
