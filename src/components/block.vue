<template>
      <div class="block" v-if="showblock" @click="stopTime">
      click me
      </div>

</template>

<script>
export default{
   props:['delay'],
data(){
    return {
        showblock:false,
        starttime:0,
        stoptime:null,
        
    }
    },
    mounted() {
        console.log("junior")
        this.timer()
        setTimeout(() => {
            this.showblock=true
            console.log(this.delay)
        },this.delay);
    },
    methods:{
        
         timer(){
             this.starttime=setInterval(() => {
                 this.stoptime+=10
             }, 100);
         },
         stopTime(){
             clearInterval(this.starttime)
             console.log(this.stoptime)
             this.showblock=false
             this.$emit('end',this.stoptime)
         }
    }

}

</script>
<style>

.block{
width:400px;
border-radius:20px;
background:#0faf87;
color:white;
    margin:40px auto;
text-align:center;
padding:100px 0;    


}
</style>