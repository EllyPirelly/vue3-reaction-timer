<template>
  <p>Reaction Time: {{ score }} ms</p>
  <p class="comment">{{ rank }}</p>
</template>

<script>
export default {
  props: ['score'],

  data() {
    return {
      rank: null,
    }
  },

  mounted() {
    if (this.score < 250) {
      this.rank = 'Chuck Norris reflexes!'
    } else if (this.score < 400) {
      this.rank = 'Machete moves!'
    } else {
      this.rank = 'well... try again, maybe?...'
    }
  },
}
</script>

<style lang="scss">
.comment {
  color: #0faf87;
  border-bottom: 2px solid #0faf87;
  display: inline-block;
  font-size: 1.4em;
  font-weight: bold;
}
</style>
