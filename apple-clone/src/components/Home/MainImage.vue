<template lang="">
  <div class="container" :style="data.id !== 1 && `margin-top: 12px;`">
    <!-- {{data}} -->
    <div class="text-wrapper">
      <h2 :class="data.text.isBlack ? `font-black` : `font-white`">{{ data.text.title }}</h2>
      <p :class="data.text.isBlack ? `font-black` : `font-white`">{{ data.text.contents }}</p>
      <p v-show="data.text.plusText !== undefined" class="plus-text">{{ data.text.plusText }}</p>
      <div class="button-wrapper">
        <MainButton v-for="buttonItem in data.button" :text="buttonItem.text" :fillTrigger="buttonItem.fillTrigger" />
        <!-- <MainButton :text="`더 알아보기`" :fillTrigger="true" />
        <MainButton :text="`구입하기`" :fillTrigger="false" /> -->
      </div>
    </div>
    <div class="image-wrapper">
      <figure class="image" :style="backgroundClass"></figure>
    </div>
  </div>
</template>
<script setup>
import MainButton from "../common/MainButton.vue";
</script>
<script>
export default {
  name: "MainImage",
  props: ["data"],
  computed: {
    backgroundClass() {
      return {
        background: `url(${this.data.backgroudImageUrl}) center no-repeat`,
      };
    },
  },
};
</script>
<style scoped>
.container {
  width: 100%;
  height: 580px;
  position: relative;
}

.text-wrapper {
  padding-top: 47px;
  position: relative;
  z-index: 2;
  text-align: center;
}
.text-wrapper > h2 {
  font-size: 56px;
  margin: 0;
}
.text-wrapper > p {
  font-size: 28px;
  margin: 6px 0 0 0;
}
.text-wrapper .plus-text{
  font-size: 18px;
  color: #ababab;
  margin-top: 16px;
}

.button-wrapper {
  margin-top: 16px;
  display: flex;
  gap: 14px;
  justify-content: center;
}

.image-wrapper {
  width: 100%;
  position: absolute;
  top: 0px;
}
.image {
  background-size: cover;
  width: 100%;
  height: 580px;
  margin: 0;
  z-index: -1;
}

.font-white {
  color: white;
}
.font-black {
  color: black;
}
</style>
