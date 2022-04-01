<template>
  <div class="block" v-if="showBlock">click me</div>
</template>

<script>
export default {
  props: ['delay'],

  data() {
    return {
      /* do not initially show Block as we want it to only show after the random delay */
      showBlock: false,
    }
  },

  mounted() {
    console.log('component mounted')
    setTimeout(() => {
      this.showBlock = true
      console.log(this.delay)
    }, this.delay)
  },

  updated() {
    console.log('component updated')
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
