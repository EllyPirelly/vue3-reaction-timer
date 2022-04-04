<template>
  <div class="block" v-if="showBlock" @click="stopTimer">click me</div>
</template>

<script>
export default {
  props: ['delay'],

  data() {
    return {
      /* do not initially show Block as we want it to only show after a random delay */
      showBlock: false,
      timer: null,
      reactionTime: 0,
    }
  },

  mounted() {
    /* console.log('component mounted') */
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },

  /* updated() {
    console.log('component updated')
  },

  // will only show when component is taken out of the DOM
  // uncomment the block component to test this
  unmounted() {
    console.log('unmounted')
  }, */

  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    },

    stopTimer() {
      clearInterval(this.timer)
      console.log(this.reactionTime)
    },
  },
}
</script>

<style lang="scss">
.block {
  background-color: #0faf87;
  border-radius: 20px;
  color: #fff;
  margin: 40px auto;
  padding: 100px 0;
  text-align: center;
  width: 400px;
}
</style>
