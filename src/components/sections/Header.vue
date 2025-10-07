<template>
  <header class="header-wrapper">
    <Swiper
      :modules="modules"
      :loop="true"
      :autoplay="false"
      :slides-per-view="1"
      :space-between="0"
      class="header-swiper__container"
      :navigation="{ nextEl: '.btn-right', prevEl: '.btn-left' }"
    >
      <SwiperSlide v-for="(slide, index) in slides" :key="index">
        <div class="slide-bg" :style="{ backgroundImage: `url(${slide.bgImage})` }"></div>
        <div class="slide-text">{{ slide.text }}</div>
      </SwiperSlide>
    </Swiper>

    <div class="container">
      <div class="header-wrap">
        <div class="header-logo">Logo company</div>

        <div class="navigation-wrap">
          <div class="btn-left"></div>
          <div class="btn-right"></div>
        </div>

        <div class="bottom-line">
          <img src="/src/assets/img/bottom-line.svg" alt="line" />
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/navigation'

const modules = [Navigation]

const slides = [
  {
    text: 'Test slider',
    bgImage: new URL('/src/assets/img/head-slide-1.png', import.meta.url).href,
  },
  {
    text: 'Owoooooo',
    bgImage: new URL('/src/assets/img/head-slide-2.png', import.meta.url).href,
  },
]
</script>

<style lang="scss" scoped>
.header-wrapper {
  position: relative;
  width: 100%;
  height: clamp(300px, 24vw, 468px);
  overflow: hidden;

  .header-swiper__container {
    width: 100%;
    height: 100%;

    .slide-bg {
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
    }

    .slide-text {
      font-weight: 400;
      font-size: clamp(40px, 10vw, 96px);
      line-height: 90%;
      text-align: center;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      color: #fff;
      z-index: 2;
    }
  }

  .container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 3;

    .header-wrap {
      display: flex;
      flex-direction: column;
      align-items: center;
      height: 100%;
      justify-content: space-between;

      .header-logo {
        margin-top: clamp(16px, 1.25vw, 24px);
        font-weight: 500;
        font-size: clamp(24px, 1.7vw, 32.42px);
        line-height: 90%;
        text-align: center;
        color: #000;
      }

      .navigation-wrap {
        display: flex;
        justify-content: space-between;
        width: 100%;
        position: relative;

        .btn-left,
        .btn-right {
          position: static;
          width: clamp(20px, 2.1vw, 40px);
          height: clamp(12px, 1.25vw, 24px);
          background-image: url('@/assets/img/arrow-left.svg');
          background-size: contain;
          background-repeat: no-repeat;
          background-position: center;
          border: none;
          cursor: pointer;
          opacity: 0.8;
          transition: opacity 0.3s;

          &:hover {
            opacity: 1;
          }

          &::after {
            display: none;
          }
        }

        .btn-right {
          transform: rotate(180deg);
        }
      }

      .bottom-line {
        margin-bottom: clamp(14px, 1.1vw, 21px);
        text-align: center;

        img {
          width: 100%;
          height: auto;
        }
      }
    }
  }
}
</style>