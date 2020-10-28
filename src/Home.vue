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
  </div>
</template>

<script>
  import RanRow from "./components/RanRow";
  import RanCol from "./components/RanCol";
  import RanButton from "./components/RanButton";
  export default {
    name: "Home",
    components: {RanButton, RanCol, RanRow}
  }
</script>

<style scoped>

</style>
