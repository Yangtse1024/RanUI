<template>
  <div>
    <!--    <ran-row :gutter="20">-->
    <!--      <ran-col :span="12">-->
    <!--        <h1 style="background-color: blue">12345</h1>-->
    <!--      </ran-col>-->
    <!--      <ran-col :span="12">-->
    <!--        <h1 style="background-color: blue">12345</h1>-->
    <!--      </ran-col>-->
    <!--      <ran-col :span="8">-->
    <!--        <h1 style="background-color: blue">12345</h1>-->
    <!--      </ran-col>-->
    <!--    </ran-row>-->
    <ran-button native-type="reset" disabled>这是一个按钮</ran-button>
    <ran-button @click="openDialog">打开弹窗</ran-button>
    <ran-dialog :visible.sync="visible" title="标题">
<!--    <ran-dialog :visible="visible" @update:visible="val => visible = val" title="标题">-->
      <p>主要内容</p>
      <span slot="foot">底部内容</span>
    </ran-dialog>
  </div>
</template>

<script>
  import RanRow from "./components/RanRow";
  import RanCol from "./components/RanCol";
  import RanButton from "./components/RanButton";
  import RanDialog from "./components/RanDialog";
  export default {
    name: "Home",
    components: {RanDialog, RanButton, RanCol, RanRow},
    data(){
      return {
        visible: false,
      }
    },
    methods:{
      openDialog(){
        console.log('fuck');
        this.visible = true;
      }
    }
  }
</script>

<style scoped>

</style>
