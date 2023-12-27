<template> 
<button v-on:click="onStart" >Start Paly</button>
<Block v-if="showBlock" :during="during" @end="onResults"/>
<Results v-if="showResult" :scoure="score"/>
</template>

<script>
import Block from './Components/Bloack.vue'
import Results from './Components/Results.vue';


export default {
  name: 'App',
  components: {
    Block,
    Results,
  },
  data(){
 return{
  showBlock: false,
  showResult: false,
  during: null,
  score: null,
 }
  },
  methods:{
    onStart(){
      this.during =0;
  this.showResult= false;
  this.showBlock = true;
  this.during = 2000 +   Math.random() * 5000;
  
  },
  onResults(res){
    this.showResult= true;
    this.score = res;
    this.showBlock = false;

    console.log('------score-----------');  
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
h1 {
color: blue;
}
</style>
