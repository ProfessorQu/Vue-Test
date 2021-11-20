<template>
  <div id="app">
    <title>Tic Tac Toe</title>

    <button @click="click(0, 0)"> </button>
    <button @click="click(0, 1)"> </button>
    <button @click="click(0, 2)"> </button>

    <button @click="click(1, 0)"> </button>
    <button @click="click(1, 1)"> </button>
    <button @click="click(1, 2)"> </button>

    <button @click="click(2, 0)"> </button>
    <button @click="click(2, 1)"> </button>
    <button @click="click(2, 2)"> </button>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      board: [
        [0, 0, 0],
        [0, 0, 0],
        [0, 0, 0]
      ],
      player: 1,
      winner: 0
    }
  },

  methods: {
    click (row, col) {
      if (this.winner) return
      if (this.board[row][col]) return
      this.board[row][col] = this.player
      this.player = this.player === 1 ? 2 : 1
      this.winner = this.checkWinner()
    },

    checkWinner () {
      const lines = [
        [0, 1, 2],
        [3, 4, 5],
        [6, 7, 8],
        [0, 3, 6],
        [1, 4, 7],
        [2, 5, 8],
        [0, 4, 8],
        [2, 4, 6]
      ]
      for (let i = 0; i < lines.length; i++) {
        const [a, b, c] = lines[i]
        if (this.board[a][b] && this.board[a][b] === this.board[c][b]) {
          return this.board[a][b]
        }
      }
      return 0
    }
  }
}
</script>
