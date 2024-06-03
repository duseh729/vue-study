<template lang="">
  <header>
    <nav>
      <ul>
        <li>logo</li>
        <li>스토어</li>
        <li>Mac</li>
        <li>iPad</li>
        <li>iPhone</li>
        <li>Watch</li>
        <li>AirPods</li>
        <li>TV 및 홈</li>
        <li>엔터테인먼트</li>
        <li>액세서리</li>
        <li>고객지원</li>
        <li>🐤</li>
        <li>🦖</li>
      </ul>
    </nav>
  </header>
</template>
<script>
export default {
  name: "Header",
};
</script>
<style scoped>
header{
  background-color: rgba(22, 22, 23);
}
/* 상위 태그에는 접근 불가 */
/* ul>li:hover header{
  background-color: tomato;
} */
nav {
  display: flex;
  width: 980px;
  margin: 0 auto;
}
ul {
  width: 100%;
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: space-between;
}
ul>li{
  padding: 0 8px;
  color: #ababab;
  font-size: 12px;
  height: 44px;
  line-height: 44px;
  font-weight: 400;
  transition: 0.5s all;
}
ul>li:hover{
  color: #FFFFFF;
  cursor: pointer;
}
</style>
