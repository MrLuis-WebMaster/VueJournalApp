<template>
  <button class="btn btn-primary">
    <i 
      class="fa fa-2x"
      :class="icon"
    ></i>
  </button>
</template>

<script>
export default {
  props: {
    icon: {
      type:String,
      default: "fa-plus"

    }
  }

}
</script>

<style lang="scss" scoped>
    button {
        text-align: center;
        vertical-align: middle;
        border-radius:100%;
        bottom: 30px;
        height: 50px;
        position: fixed;
        right: 30px;
        width: 50px;
    }
</style>