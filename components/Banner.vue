<template>
  <div class="banner">
    <div class="title-wrapper">
      <h1 class="title">Mable</h1>
      <p class="subtitle">地図をあなたの生活空間に</p>
    </div>
    <el-carousel :interval="5000" indicator-position="outside">
      <el-carousel-item v-for="item in 4" :key="item"></el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
import { Carousel, CarouselItem } from 'element-ui'

export default {
  components: {
    'el-carousel': Carousel,
    'el-carousel-item': CarouselItem
  }
}
</script>

<style>
.banner {
  margin-top: 60px;
}

.title-wrapper {
  position: absolute;
  z-index: 9;
  top: calc(50vh - 60px);
  width: 100%;
  pointer-events: none;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  color: #fff;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  color: #fff;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.el-carousel {
  width: 100vw;
}

.el-carousel__container {
  height: calc(100vh - 60px);
}

.el-carousel__item {
  background-size: cover;
}

.el-carousel__item:nth-child(4n) {
  background: url("/banner1.jpg") center;
  background-size: cover;
}

.el-carousel__item:nth-child(4n+1) {
  background: url("/banner2.jpg") center;
  background-size: cover;
}

.el-carousel__item:nth-child(4n+2) {
  background: url("/banner3.jpg") center;
  background-size: cover;
}

.el-carousel__item:nth-child(4n+3) {
  background: url("/banner4.jpg") center;
  background-size: cover;
}
</style>
