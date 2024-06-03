<template lang="">
  <div>
    <!-- {{phoneData}} -->
    <MainImage v-for="data in phoneData" :data="data" :key="data.id" />
  </div>
</template>
<script setup>
import { ref } from "vue";
import MainImage from "../components/Home/MainImage.vue";

const phoneData = ref([
      {
        id: 1,
        text: { title: "iPhone 15 Pro", contents: "티타늄.초강력.초경량.초프로." },
        button: { button1: { text: "더 알아보기", fillTrigger: true }, button2: { text: "구입하기", fillTrigger: false } },
        backgroudImageUrl: "https://www.apple.com/v/home/bn/images/heroes/iphone-15-pro/hero_iphone15pro__i70z9oz3hj2i_large.jpg",
      },
      {
        id: 2,
        text: { title: "iPhone 15", contents: "새로운 카메라.새로운 디자인.새로움이 물씬.", isBlack: true },
        button: { button1: { text: "더 알아보기", fillTrigger: true }, button2: { text: "구입하기", fillTrigger: false } },
        backgroudImageUrl: "https://www.apple.com/v/home/bn/images/heroes/iphone-15/hero_iphone15_announce__uuemlcwczn6u_large.jpg",
      },
      {
        id: 3,
        text: { title: "iPad Pro", contents: "놀라우리만치 얇다. 엄청나게 강력하다.", plusText: "6월 8일 주문 시작. 6월 19일 출시." },
        button: { button1: { text: "더 알아보기", fillTrigger: true }, button2: { text: "가격 보기", fillTrigger: false } },
        backgroudImageUrl: "https://www.apple.com/v/home/bn/images/heroes/ipad-pro/hero_ipadpro_announce__gi60pcfhpeie_large.jpg",
      },
    ]);
</script>
<style lang=""></style>
