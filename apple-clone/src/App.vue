<template lang="">
  <div>
    <Header />
      <router-view></router-view>
  </div>
</template>
<script setup>
import Header from './components/common/Header.vue'
</script>
<script>
export default {
  name: "App"
}
</script>
<style lang="">
  
</style>