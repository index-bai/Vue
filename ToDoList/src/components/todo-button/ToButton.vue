<template>
  <div class="btn-group mt-3 btn-container" role="group" aria-label="Basic example">
    <button type="button" class="btn btn-primary" :class='active === 0? "btn-primary" : "btn-secondary"' @click="onBtnClick(0)">全部</button>
    <button type="button" class="btn" :class='active === 1 ? "btn-primary" : "btn-secondary"' @click="onBtnClick(1)">已完成</button>
    <button type="button" class="btn" :class='active === 2 ? "btn-primary" : "btn-secondary"' @click="onBtnClick(2)">未完成</button>
  </div>
</template>

<script>
export default {
  name: "ToButton",
  props:{
      active:{
          type:Number,
          required:true,
          default:0,
      },
  },
  emits:['update:active'],
  methods:{
      onBtnClick(index){
          console.log(index,this.active);
        //   忘写一个等号
          if(index == this.active) return;
          this.$emit('update:active',index)
      }
  }
};
</script>

<style lang:'less' scoped>
    .btn-container{
        width: 230px;
        text-align: center;
    }
</style>