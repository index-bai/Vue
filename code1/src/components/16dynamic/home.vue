<template>
  <h1>home{{ count }}</h1>
  <button type="button" class="btn btn-primary" @click="count+=1">+1</button>
</template>

<script>
export default {
    name:'MyHome',
    data(){
        return{
            count:0
        }
    },
    created(){
        console.log('created');
    },
    unmounted(){
        console.log('unmounted');
    }
}
</script>

<style>

</style>