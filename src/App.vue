<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">
    press to play and wait for the buzzer to appear...
  </button>
  <Block v-if="isPlaying" :delay="delay" @passReactiontime="endGame" />
  <Results v-if="showResults" :score="score" />
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',

  components: {
    Block,
    Results,
  },

  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    }
  },

  methods: {
    start() {
      /* calculates a number between 2 and 7 seconds */
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },

    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
    },
  },
}
</script>

<style lang="scss">
#app {
  color: #2c3e50;
  font-family: 'Bitter', serif;
  margin-top: 60px;
  text-align: center;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

button {
  background-color: #0faf87;
  border: none;
  border-radius: 4px;
  color: #fff;
  cursor: pointer;
  font-family: 'Bitter', serif;
  font-size: 16px;
  font-weight: bold;
  margin: 10px;
  padding: 12px 16px;

  &[disabled] {
    cursor: not-allowed;
    opacity: 0.4;
  }

  &:hover:not([disabled]) {
    background-color: #9df1dc;
    color: #2c3e50;
  }
}
</style>
