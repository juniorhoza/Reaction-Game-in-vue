<template >
    <div>
        <p> your reaction time was  <span class="gre">{{time}}</span>  ms</p>
    </div>
</template>
<script>
export default {
    props:["time"],

    data(){
        return{
             
        }
    },
}
</script>
<style>
    .gre{
    font-weight:bold;
    color:#0faf87;  
    
    
    }
</style>