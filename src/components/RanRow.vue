<script>
  export default {
    name: "RanRow",
    componentName: 'RanRow',
    props:{
      tag:{
        type: String,
        default: 'div'
      },
      gutter:{
        type: Number,
        default: 0
      }
    },
    render(h) {
      return h(
        this.tag,
        {
          class: ['ran-row']
        },
        this.$slots.default
      )
    }
  }
</script>

<style scoped>
  .ran-row{
    position: relative;
    box-sizing: border-box;
  }
</style>
