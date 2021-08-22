<template>
  <h1>Vut Reaction Timer</h1>
  <button @click="start" :disabled="isplaying">Play</button>
  <Block v-if="isplaying" :delay="delay" @end="endGame" />
  <Result v-if="showResult" :score="score"/>

  <!-- <p v-if="showResult">Reaction Time: {{ score }}</p> -->
</template>

<script>
import Block from "./components/Block.vue";
import Result from "./components/Result.vue";

export default {
  name: "App",
  components: {
    Block,
    Result,
  },
  data() {
    return {
      isplaying: false,
      delay: null,
      score: null,
      showResult: false,
    };
  },
  methods: {
    start() {
      this.isplaying = true;
      this.delay = 2000 + Math.random() * 5000;
      console.log(this.delay);
      this.showResult = false;
    },
    endGame(reactionTimePassed) {
      this.score = reactionTimePassed;
      this.isplaying = false;
      this.showResult = true;
    },
  },
};
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
button{
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
button[disabled]{
  cursor: not-allowed;
  opacity: 0.2ttttttttttttttttttdhhjdks5tdttttgyttttttt5ttttttttttttgggtttttttgtgft;
}
</style>
