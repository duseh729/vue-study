<template lang="">
  <div class="container" :style="[ { 'align-items': `flex-${data.position}` }]">
    <!-- {{data}} -->
    <div class="text-wrapper" >
      <h2 v-if="data.text.title !== undefined" :class="data.text.isBlack ? `font-black` : `font-white`">{{ data.text.title }}</h2>
      <h3 v-else :style="h2Image"><span class="visually-hidden">2024년 Apple WWDC(세계개발자회의)</span></h3>
      <!-- v-html을 이용해 \n -> <br>로 변경 -->
      <p v-html="contents" :class="data.text.isBlack ? `font-black` : `font-white`"></p>
      <p v-show="data.text.plusText !== undefined" class="plus-text">{{ data.text.plusText }}</p>
      <div class="button-wrapper">
        <MainButton v-for="buttonItem in data.button" :text="buttonItem.text" :fillTrigger="buttonItem.fillTrigger" :small="true" />
        <!-- <MainButton :text="`더 알아보기`" :fillTrigger="true" />
        <MainButton :text="`구입하기`" :fillTrigger="false" /> -->
      </div>
    </div>
    <div class="image-wrapper">
      <figure v-if="data.isVideo !== true" class="image" :style="backgroundClass"></figure>
      <video v-else style="object-fit: cover" class="image" autoplay muted loop preload="none" data-inline-media>
        <source :src="data.backgroudImageUrl" type="video/mp4" />
      </video>
    </div>
  </div>
</template>
<script setup>
import MainButton from "../common/MainButton.vue";
</script>
<script>
export default {
  name: "SubImage",
  props: ["data"],
  computed: {
    backgroundClass() {
      return {
        background: `url(${this.data.backgroudImageUrl}) center no-repeat`,
      };
    },
    contents() {
      return this.data.text.contents.replaceAll("\n", "<br />");
    },
    h2Image() {
      return {
        "background-image": `url(${this.data.text.titleImage})`,
        "background-position": "center",
        "background-size": this.data.text.titleImageSize,
        "background-repeat": "no-repeat",
        height: this.data.text.titleImageSize.split(" ")[1],
        "margin-bottom" : "14px"
      };
    },
  },
};
</script>
<style scoped>
.container {
  width: 49%;
  height: 580px;
  position: relative;
  padding: 47px 0;
  display: flex;
  justify-content: center;
  margin-top: 12px;
}

.text-wrapper {
  position: relative;
  z-index: 2;
  text-align: center;
}
.text-wrapper > h2 {
  font-size: 34px;
  margin: 0;
}
.text-wrapper > p {
  font-size: 18px;
  margin: 6px 0 0 0;
}
.text-wrapper .plus-text {
  font-size: 16px;
  color: #6c6c6c;
  margin-top: 12px;
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

.visually-hidden {
  position: absolute;
  clip: rect(1px, 1px, 1px, 1px);
  -webkit-clip-path: inset(0px 0px 99.9% 99.9%);
  clip-path: inset(0px 0px 99.9% 99.9%);
  overflow: hidden;
  height: 1px;
  width: 1px;
  padding: 0;
  border: 0;
}
</style>
