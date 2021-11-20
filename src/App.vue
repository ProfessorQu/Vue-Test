<template>
  <div id="app">
    <h1>{{ title }}</h1>

    <button v-on:click="toggleMessage">Toggle</button>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      title : "Welcome!"
    }
  },

  methods: {
    toggleMessage () {
      this.title = this.title === "Welcome!" ? "Goodbye!" : "Welcome!"
    }
  }
}
</script>
