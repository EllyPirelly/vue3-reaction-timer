<template>
  <div class="buzzer" v-if="showBlock" @click="stopTimer">hit me</div>
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
      this.$emit('passReactiontime', this.reactionTime)
    },
  },
}
</script>

<style lang="scss">
.buzzer {
  align-items: center;
  background-color: #9df1dc;
  border-radius: 50%;
  box-shadow: 0 9px #2c3e50;
  color: #2c3e50;
  cursor: pointer;
  display: flex;
  font-size: 24px;
  height: 300px;
  justify-content: center;
  margin: 20px auto;
  width: 300px;

  &:active {
    background-color: #0faf87;
    box-shadow: 0 5px #2c3e50;
    color: #fff;
    transform: translateY(4px);
  }
}
</style>
