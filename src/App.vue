<template>
  <h1>Reaction Timer Challenge</h1>
  <button class="plat-btn" @click="start" :disabled="isPlaying">Play Now</button> <!--disabled button during playing-->
  <div v-if="loading">
      <img src="@/assets/loading.gif" alt="Loading..." width="100" />
  </div>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
      loading: false
    }
  },
  methods: {
    start() {
      this.loading = true;
      this.delay = 2000 + Math.random() * 5000 //adding rand delay
      this.isPlaying = true // by true stating yes user is playing
      // console.log(this.delay) // just to check delay
      this.showResults = false
      // Make the loading disappear 1 second before the block appears
      const blockDisplayTime = 1; // Time (in seconds) to wait before showing the block
      const totalDelay = this.delay - (blockDisplayTime * 300); // Adjust total delay

      // Set a timeout to handle the loading and block appearance
      setTimeout(() => {
        this.loading = false; // Hide loading
        this.isPlaying = true; // Show the block
      }, totalDelay);
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
      this.loading = false; // Reset loading state
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
button {
  background: #0faf87;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
