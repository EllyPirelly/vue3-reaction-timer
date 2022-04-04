<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @passReactiontime="endGame" />
  <p v-if="showResults">Reaction Time: {{ score }} ms</p>
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',

  components: {
    Block,
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
</style>
