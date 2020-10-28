<template>
  <div class="ran-dialog__wrapper" v-show="visible">
    <div class="ran-dialog" :style="style">
      <div class="ran-dialog__header">
        <span class="ran-dialog__title">{{title}}</span>
        <button class="ran-dialog__headerbtn" @click="handleClose">×</button>
      </div>
      <div class="ran-dialog__body">
        <slot></slot>
      </div>
      <div class="ran-dialog__footer">
        <slot name="foot"></slot>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "RanDialog",
    props:{
      title: {
        type: String,
        default: ""
      },
      visible: {
        type: Boolean,
        default: false,
      },
      width: {
        type:  String,
        default: '50%'
      }
    },
    methods: {
      handleClose(){
        this.$emit('update:visible', false);
      },
      test(){
        console.log(this.$el);
      }
    },
    computed:{
      style(){
        let style = {};
        style.width = this.width;
        return style;
      }
    },
    mounted() {
      console.log(this.$el);
    }
  }
</script>

<style scoped>
  div.ran-dialog__wrapper{
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    margin: 0;
    background-color: rgba(0,0,0,0.2);
  }
  div.ran-dialog{
    box-sizing: border-box;
    position: fixed;
    min-height: 100px;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    border-radius: 4px;
  }
  div.ran-dialog__header{
    height: 3rem;
    padding: 20px 20px 10px;
  }
  span.ran-dialog__title{
    float: left;
    font-size: 1.2rem;
  }
  button.ran-dialog__headerbtn{
    float: right;
    outline: none;
    background-color: rgba(0,0,0,0);
    border: none;
    cursor: pointer;
  }
</style>
