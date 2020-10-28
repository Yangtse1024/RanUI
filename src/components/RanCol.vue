<script>
  export default {
    props: {
      span: {
        type: Number,
        default: 24
      },
      tag: {
        type: String,
        default: 'div'
      }
    },
    name: "RanCol",
    computed:{
      gutter(){
        let parent = this.$parent;
        while (parent && parent.$options.componentName !== 'RanRow'){
          parent = parent.$parent;
        }
        return parent ? parent.gutter : 0;
      }
    },
    data(){
      return {
        style:{},
      }
    },
    render(h){
      let style = {};
      if (this.gutter) {
        style.paddingLeft = this.gutter / 2 + 'px';
        style.paddingRight = style.paddingLeft;
      }
      let classList = [
        'ran-col',
        `ran-col-${this.span}`
      ]
      return h(
        this.tag,
        {
          class: classList,
          style
        },
        this.$slots.default
      )
    }
  }
</script>

<style scoped>
  [class*=ran-col-]{
    float: left;
    box-sizing: border-box;
  }
  .ran-col-24{
    width: 100%;
  }
  .ran-col-12{
    width: 50%;
  }
  .ran-col-8{
    width: 33.33333%;
  }
  .ran-col-6{
    width: 25%;
  }
  .ran-col-4{
    width: 16.66667%;
  }
  .ran-col-3{
    width: 12.5%;
  }
  .ran-col-2{
    width: 8.33333%;
  }
  .ran-col-1 {
    width: 4.16667%;
  }
</style>
