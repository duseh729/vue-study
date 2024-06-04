<template lang="">
  <!-- {{small}} -->
  <button :class="fillTrigger && `fill`" :style="small && `padding: 8px 12px;`" >{{ text }}</button>
</template>
<script>
export default {
  name: "MainButton",
  props: {
    text: {
      type: String,
      required: true,
    },
    fillTrigger:{
      type: Boolean,
      required: false
    },
    small:{
      type: Boolean,
      required: false
    }
  },
};
</script>
<style scoped>
  button{
    border: 1px solid #0071e3;
    border-radius: 20px;
    padding: 11px 21px;
    background-color: transparent;
    color: #0071e3;
    font-weight: 600;
  }
  button:hover{
    background-color: #0077ED;
    color: white;
  }

  .fill{
    background-color: #0071e3;
    color: white;
  }
</style>
