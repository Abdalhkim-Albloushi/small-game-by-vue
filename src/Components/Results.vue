<template>
  <h1>Reslt : {{ scoure }}ms</h1>
  <h1>{{ text }}</h1>
</template>

<script>
export default {
    data(){
        return{
            text: '',        
        }
    },
    mounted(){
        if(this.scoure< 200){
    this.text= 'Great';
}else if(this.scoure <400){
    this.text = 'Good';
}else{
    this.text = 'Bad';
}
    },
    props:['scoure'],


}
</script>


<style>

</style>