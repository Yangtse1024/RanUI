<template>
  <button
    :type="nativeType"
    :disabled="loading || disabled"
    :class="[
      'ran-button--' + type,
      'ran-button',
      {
        'is-round': round,
        'is-circle': circle,
        'is-disabled': disabled,
        'is-loading': loading
      }
    ]">
    <span v-if="$slots.default"><slot></slot></span>
  </button>
</template>

<script>
  export default {
    name: "RanButton",
    props:{
      type: {
        type: String,
        default: 'default'
      },
      nativeType:{
        type: String,
        default: 'button'
      },
      loading:{
        type: Boolean,
        default: false,
      },
      disabled:{
        type: Boolean,
        default: false
      },
      round: {
        type: Boolean,
        default: false
      },
      circle: {
        type: Boolean,
        default: false
      }
    }
  }
</script>

<style scoped>
  .ran-button{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 2rem;
    line-height: 2rem;
    text-align: center;
    outline: none;
    cursor: pointer;
    white-space: nowrap;
    border-radius: 0.25rem;
    background-color: #fff;
    border: 1px solid #dcdfe6;
    padding: 0.75rem;
  }
  .ran-button.is-round {
    border-radius: 1.25rem;
  }
  .ran-button.ran-button--default:hover, .ran-button.ran-button--default:focus{
    color: #409eff;
    border-color: #c6e2ff;
    background-color: #ecf5ff;
  }

</style>
