<template>
  <div class="result-con">
    <h2>This is Your Result</h2>
    <p>Result Time: {{ score }}ms</p>
    <p class="rank">{{ rank }}</p>
  </div>
</template>

<script>
export default {
  props: ["score"],
  data () {
      return {
          rank: null,
      }
  },
  mounted () {
      if(this.score < 250){
          this.rank = "Ninja Fingers"
      }else if(this.score < 400){
           this.rank = "Rapid Reflexes"
      }else{
          this.rank = "Snail pace"
      }
  }
};
</script>

<style>
.result-con {
  background: #000;
  color: white;
  width: 400px;
  border-radius: 20px;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
.rank{
    font-size: 1.4em;
    color: #0faf87;
    font-weight: bold;
}
</style>
