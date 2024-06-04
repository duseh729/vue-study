<template lang="">
  <div>
    <!-- {{phoneData}} -->
    <MainImage v-for="data in mainImageData" :data="data" :key="data.id" />
    <div class="sub-image-wrapper">
      <SubImage v-for="data in subImageData" :data="data" :key="data.id" />
    </div>
  </div>
</template>
<script setup>
import { ref } from "vue";
import MainImage from "../components/Home/MainImage.vue";
import SubImage from "../components/Home/SubImage.vue";

const mainImageData = ref([
  {
    id: 1,
    text: {
      titleImage: "https://www.apple.com/v/home/bn/images/logos/wwdc24-announce/hero_logo_wwdc24_announce__bdetzb0yh2k2_large.png",
      contents: `Apple WWDC(세계개발자회의).\n한국 시간 6월 11일-15일, 온라인에서 만나요.`,
    },
    button: { button1: { text: "더 알아보기", fillTrigger: true } },
    backgroudImageUrl: "https://www.apple.com/105/media/us/home/2024/9ca55411-d96c-4ea2-9cec-9b5eff7d5e94/anim/2line/large.mp4",
    isVideo: true,
    position: "end",
  },
  {
    id: 2,
    text: { title: "iPhone 15 Pro", contents: "티타늄.초강력.초경량.초프로." },
    button: { button1: { text: "더 알아보기", fillTrigger: true }, button2: { text: "구입하기", fillTrigger: false } },
    backgroudImageUrl: "https://www.apple.com/v/home/bn/images/heroes/iphone-15-pro/hero_iphone15pro__i70z9oz3hj2i_large.jpg",
    position: "start",
  },
  {
    id: 3,
    text: { title: "iPad Pro", contents: "놀라우리만치 얇다. 엄청나게 강력하다.", plusText: "6월 8일 주문 시작. 6월 19일 출시." },
    button: { button1: { text: "더 알아보기", fillTrigger: true }, button2: { text: "가격 보기", fillTrigger: false } },
    backgroudImageUrl: "https://www.apple.com/v/home/bn/images/heroes/ipad-pro/hero_ipadpro_announce__gi60pcfhpeie_large.jpg",
    position: "start",
  },
]);

const subImageData = ref([
  {
    id: 1,
    text: { title: "iPhone 15", contents: "새로운 카메라, 새로운 디자인, 새로움이 물씬", isBlack: true },
    button: { button1: { text: "더 알아보기", fillTrigger: true }, button2: { text: "구입하기", fillTrigger: false } },
    backgroudImageUrl: "https://www.apple.com/v/home/bn/images/promos/iphone-15/promo_iphone15_announce__fmxxi8r9fkuy_large.jpg",
    position: "start",
  },
  {
    id: 2,
    text: { title: "대학생", contents: "Mac 그리고 iPad. 훌쩍 앞서다." },
    button: { button1: { text: "더 알아보기", fillTrigger: true } },
    backgroudImageUrl: "https://www.apple.com/v/home/bn/images/promos/college-students/promo_college_students__bxqdcoxgjzw2_large.jpg",
    position: "end",
  },
  {
    id: 3,
    text: { title: "Macbook Air", contents: "날렵하게. 강력하게. M3답게", isBlack: true },
    button: { button1: { text: "더 알아보기", fillTrigger: true }, button2: { text: "구입하기", fillTrigger: false } },
    backgroudImageUrl: "https://www.apple.com/v/home/bn/images/promos/macbook-air-m3/promo_macbook_air_m3__e43jegok3wuq_large.jpg",
    position: "start",
  },
  {
    id: 4,
    text: { titleImage: "https://www.apple.com/v/home/bn/images/logos/apple-watch-series-9/promo_logo_apple_watch_series_9__ckz0hbex0yeu_large.png", titleImageSize: "138px 53px", contents: "보다 똑똑. 보다 또렷. 보다 강력." },
    button: { button1: { text: "더 알아보기", fillTrigger: true }, button2: { text: "구입하기", fillTrigger: false } },
    backgroudImageUrl: "https://www.apple.com/kr/home/bn/images/promos/apple-watch-series-9/promo_apple_watch_series_9_order__b3u85rm9zf6u_large.jpg",
    position: "start",
  },
  {
    id: 5,
    text: { titleImage: "https://www.apple.com/v/home/bn/images/logos/ipad-air/promo_logo_ipadair__frwnnsqveeye_large.png", titleImageSize: "144px 33px" , contents: "두 가지 사이즈. 더 빠른 칩. 무엇이든 거뜬하게.", plusText: "6월 8일 주문 시작. 6월 19일 출시.", isBlack: true },
    button: { button1: { text: "더 알아보기", fillTrigger: true }, button2: { text: "가격 보기", fillTrigger: false } },
    backgroudImageUrl: "https://www.apple.com/v/home/bn/images/promos/ipad-air/promo_ipadair_announce__eqsaj3vip4om_large.jpg",
    position: "start",
  },
  {
    id: 6,
    text: { titleImage: "https://www.apple.com/v/home/bn/images/logos/iphone-tradein/logo_tradein__d1fpktgipvki_large.png", titleImageSize: "155px 32px", contents: `iPhone11 이상의 모델을 보상 판매하면\n\\200,000-\\950,000\n상당의 크레딧이.`, isBlack: true },
    button: { button1: { text: "견적 확인하기", fillTrigger: true } },
    backgroudImageUrl: "https://www.apple.com/v/home/bn/images/promos/iphone-tradein/promo_iphone_tradein__bugw15ka691e_large.jpg",
    position: "start",
  },
]);
</script>
<style scoped>
.sub-image-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 0 14px;
}
</style>
