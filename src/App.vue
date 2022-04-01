<template>
  <h1>Reaction Timer</h1>
  <button @click="start">play</button>
</template>

<script>
export default {
  name: 'App',

  components: {
    //
  },

  data() {
    return {
      isPlaying: false,
      delay: null,
    }
  },

  methods: {
    start() {
      /* calculates a number between 2 and 7 seconds */
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      console.log(this.delay)
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
