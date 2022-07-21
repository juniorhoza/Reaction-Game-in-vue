<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="play" :disabled="is_playing">play</button>
  <!-- <p v-if="display"> your reaction tome was : {{score}} Ms</p> -->
  <block  v-if="is_playing" :delay="delay" @end="endGame"/>
  <result  v-if="display" :time="score"/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import block from './components/block.vue'
import result from './components/result.vue'

export default {
  name: 'App',
  components: {
    block,
    result,
  },
  data(){
    return {
      is_playing:false,
      delay:null,
      score:null,
      display:false,

    }
  },
  methods:{
    play(){
      this.delay=2000 +  Math.random()*5000
      this.is_playing=true
      this.display=false
      console.log(this.delay)
    },
    endGame(stoptime){
      this.score=stoptime
      this.is_playing=false
      this.display=true
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
