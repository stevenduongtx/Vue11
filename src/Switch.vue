<template>
    <div>
        <div id="on"
             @click="switched(true)"
            :class="{active : value}"
        > On
        </div>

        <div id="off"
             @click="switched(false)"
             :class="{active : !value}"
        > Off
        </div>
    </div>
</template>
<script>
    export default {
       props:['value'],
        methods:{
           switched(isOn){
               this.$emit('input',isOn);
           }
        }
    }
</script>
<style scoped>
    #on,#off{
        width:40px;
        height:20px;
        display:inline-block;
        background-color:lightgray;
        cursor:pointer;
        padding:2px;
        margin:10px -2px;
        box-sizing:content-box;
        text-align: center;
    }

    #on.hover,#on.active{
        background-color:lightgreen;
    }

    #off.hover,#off.active{
        background-color:lightcoral;
    }

</style>