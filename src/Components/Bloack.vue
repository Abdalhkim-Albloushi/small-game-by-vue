<template>
   <div v-if="startPaly" class="block" @click="onEnd"><h1>Click me </h1></div> 
</template>


<script>
export default {
    props:['during'],
    
    data(){
        return{
            startPaly:false,
            resultTime:0,
            time:null,
        }
    },
    mounted() {
    setTimeout(() => {
        console.log('Paly')
    this.startPaly =true;
    this.onSart()
   
},
    this.during);
    },
    methods: {
 
    onEnd(){
    this.startPaly= false;
    console.log(this.time);
    clearInterval(this.time);
    this.$emit('end',this.resultTime);
   
    },
    onSart(){
    this.time = setInterval(() => {
    this.resultTime += 10
    }, 10);


    },
}

    
    
   
}
</script>

<style >
.block{
    text-align: center;
align-content: center;
display: block;
    background-color: rgb(5, 5, 87);
  margin-top: 60px;
  width: 400px;
  height: 300px;
  border-radius: 20%;
  padding: 100px 0;
  margin: 40px auto;
}
.block h1{
color:bisque;

}
</style>