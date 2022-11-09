<template>
  <section id="sliderType" class="slider__inner nexon">
    <swiper
      :spaceBetween="30"
      :centeredSlides="true"
      :autoplay="{
        delay: 5000,
        disableOnInteraction: false,
      }"
      :pagination="{
        clickable: true,
      }"
      :navigation="true"
      :modules="modules"
      class="mySwiper"
    >
      <swiper-slide v-for="st in sliderText" :key="st">
        <div class="desc">
          <span>{{ st.small }}</span>
          <h3>{{ st.big }}</h3>
          <p>
            {{ st.desc }}
          </p>
          <div class="btn">
            <a href="/">{{ st.btn1 }}</a>
            <a href="/" class="black">{{ st.btn2 }}</a>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </section>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";
// Import Swiper styles
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/navigation";
// import required modules
import { Autoplay, Pagination, Navigation } from "swiper";
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Autoplay, Pagination, Navigation],
    };
  },
  data() {
    return {
      sliderText: [
        {
          small: "NAVER WORKS",
          big: "네이버웍스 시작을 위한 첫 단계!",
          desc: "상품 신청부터 도메인 소유권 확인/구성원 추가/ 그룹 만들기까지 무료 셋업 지원",
          btn1: "자세히 보기",
          btn2: "정보 보기",
        },
        {
          small: "NAVER WORKS",
          big: "네이버웍스 시작을 위한 첫 단계!",
          desc: "상품 신청부터 도메인 소유권 확인/구성원 추가/ 그룹 만들기까지 무료 셋업 지원",
          btn1: "자세히 보기",
          btn2: "정보 보기",
        },
        {
          small: "NAVER WORKS",
          big: "네이버웍스 시작을 위한 첫 단계!",
          desc: "상품 신청부터 도메인 소유권 확인/구성원 추가/ 그룹 만들기까지 무료 셋업 지원",
          btn1: "자세히 보기",
          btn2: "정보 보기",
        },
      ],
    };
  },
};
</script>
<style>
.slider__inner {
  margin-top: 70px;
}
.slider {
}
.slider__img {
  background: url(../../assets/img/slider_bg01_01.jpg) no-repeat center / cover;
}

.slider__arrow a {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 30px;
  height: 56px;
  background-image: url(../../assets/img/slider_icon.svg);
}
.slider__arrow a.left {
  left: 20px;
}
.slider__arrow a.right {
  right: 20px;
  background-position: -50px 0;
}
.slider__dot {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: 25px;
}
.slider__dot a {
  display: inline-block;
  width: 16px;
  height: 16px;
  background-image: url(../../assets/img/slider_icon.svg);
  background-position: -20px -70px;
}
.slider__dot a.active {
  background-position: 0px -70px;
}
.slider__dot a.play {
  background-position: -40px -70px;
}
.slider__dot a.stop {
  background-position: -60px -70px;
}
/* swiper */
.swiper-slide {
  background: url(../../assets/img/slider_bg01_01.jpg) no-repeat center / cover;
}
.swiper-slide .desc {
  width: 1160px;
  margin: 0 auto;
  padding: 100px 20px;
  box-sizing: border-box;
  z-index: 0;
}
.swiper-slide .desc span {
  font-size: 16px;
  background-color: #fff;
  padding: 1px 14px 0 14px;
  border: 30px;
  text-transform: uppercase;
  margin-bottom: 10px;
  display: inline-block;
}
.swiper-slide .desc h3 {
  font-size: 110px;
  font-weight: 300;
  line-height: 1;
  color: #fff;
  text-transform: uppercase;
  margin-bottom: 16px;
  margin-left: -8px;
}
.swiper-slide .desc p {
  font-size: 20px;
  font-weight: 300;
  color: #fff;
  line-height: 1.35;
  margin-bottom: 130px;
}
.swiper-slide .desc .btn {
}
.swiper-slide .desc .btn a {
  font-size: 16px;
  background-color: #fff;
  padding: 11px 50px;

  display: inline;
}
.swiper-slide .desc .btn a.black {
  background: #000;
  color: #fff;
}
.swiper-button-next,
.swiper-button-prev {
  width: 30px !important;
  height: 56px !important;
  background-image: url(../../assets/img/slider_icon.svg);
}
.swiper-button-next {
  background-position: -50px 0;
}
.swiper-button-next::after,
.swiper-button-prev::after {
  opacity: 0;
}

.swiper-pagination-bullet {
  width: 16px !important;
  height: 16px !important;
  background-image: url(../../assets/img/slider_icon.svg) !important;
  background-position: -20px -70px !important;
  background-color: transparent !important;
  opacity: 1 !important;
}
.swiper-pagination-bullet-active {
  background-position: 0 -70px !important;
}
/* media */
@media (max-width: 960px) {
  .swiper-slide .desc {
    width: 100%;
    text-align: center;
  }
  .swiper-slide .desc h3 {
    font-size: 70px;
    word-break: keep-all;
  }
}
@media (max-width: 600px) {
  .swiper-slide .desc {
    padding: 80px 0;
  }
  .swiper-slide .desc h3 {
    font-size: 40px;
  }
  .swiper-slide .desc p {
    font-size: 16px;
    margin-bottom: 50px;
  }
  .swiper-slide .desc .btn a {
    padding: 10px 25px;
  }
}
</style>

<style>
/**
 * Swiper 8.3.2
 * Most modern mobile touch slider and framework with hardware accelerated transitions
 * https://swiperjs.com
 *
 * Copyright 2014-2022 Vladimir Kharlampidi
 *
 * Released under the MIT License
 *
 * Released on: July 26, 2022
 */

@font-face {
  font-family: swiper-icons;
  src: url("data:application/font-woff;charset=utf-8;base64, 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");
  font-weight: 400;
  font-style: normal;
}
:root {
  --swiper-theme-color: #fff;
}
.swiper {
  margin-left: auto;
  margin-right: auto;
  position: relative;
  overflow: hidden;
  list-style: none;
  padding: 0;
  z-index: 1;
}
.swiper-vertical > .swiper-wrapper {
  flex-direction: column;
}
.swiper-wrapper {
  position: relative;
  width: 100%;
  height: 100%;
  z-index: 1;
  display: flex;
  transition-property: transform;
  box-sizing: content-box;
}
.swiper-android .swiper-slide,
.swiper-wrapper {
  transform: translate3d(0px, 0, 0);
}
.swiper-pointer-events {
  touch-action: pan-y;
}
.swiper-pointer-events.swiper-vertical {
  touch-action: pan-x;
}
.swiper-slide {
  flex-shrink: 0;
  width: 100%;
  height: 100%;
  position: relative;
  transition-property: transform;
}
.swiper-slide-invisible-blank {
  visibility: hidden;
}
.swiper-autoheight,
.swiper-autoheight .swiper-slide {
  height: auto;
}
.swiper-autoheight .swiper-wrapper {
  align-items: flex-start;
  transition-property: transform, height;
}
.swiper-backface-hidden .swiper-slide {
  transform: translateZ(0);
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}
.swiper-3d,
.swiper-3d.swiper-css-mode .swiper-wrapper {
  perspective: 1200px;
}
.swiper-3d .swiper-cube-shadow,
.swiper-3d .swiper-slide,
.swiper-3d .swiper-slide-shadow,
.swiper-3d .swiper-slide-shadow-bottom,
.swiper-3d .swiper-slide-shadow-left,
.swiper-3d .swiper-slide-shadow-right,
.swiper-3d .swiper-slide-shadow-top,
.swiper-3d .swiper-wrapper {
  transform-style: preserve-3d;
}
.swiper-3d .swiper-slide-shadow,
.swiper-3d .swiper-slide-shadow-bottom,
.swiper-3d .swiper-slide-shadow-left,
.swiper-3d .swiper-slide-shadow-right,
.swiper-3d .swiper-slide-shadow-top {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 10;
}
.swiper-3d .swiper-slide-shadow {
  background: rgba(0, 0, 0, 0.15);
}
.swiper-3d .swiper-slide-shadow-left {
  background-image: linear-gradient(
    to left,
    rgba(0, 0, 0, 0.5),
    rgba(0, 0, 0, 0)
  );
}
.swiper-3d .swiper-slide-shadow-right {
  background-image: linear-gradient(
    to right,
    rgba(0, 0, 0, 0.5),
    rgba(0, 0, 0, 0)
  );
}
.swiper-3d .swiper-slide-shadow-top {
  background-image: linear-gradient(
    to top,
    rgba(0, 0, 0, 0.5),
    rgba(0, 0, 0, 0)
  );
}
.swiper-3d .swiper-slide-shadow-bottom {
  background-image: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0.5),
    rgba(0, 0, 0, 0)
  );
}
.swiper-css-mode > .swiper-wrapper {
  overflow: auto;
  scrollbar-width: none;
  -ms-overflow-style: none;
}
.swiper-css-mode > .swiper-wrapper::-webkit-scrollbar {
  display: none;
}
.swiper-css-mode > .swiper-wrapper > .swiper-slide {
  scroll-snap-align: start start;
}
.swiper-horizontal.swiper-css-mode > .swiper-wrapper {
  scroll-snap-type: x mandatory;
}
.swiper-vertical.swiper-css-mode > .swiper-wrapper {
  scroll-snap-type: y mandatory;
}
.swiper-centered > .swiper-wrapper::before {
  content: "";
  flex-shrink: 0;
  order: 9999;
}
.swiper-centered.swiper-horizontal
  > .swiper-wrapper
  > .swiper-slide:first-child {
  margin-inline-start: var(--swiper-centered-offset-before);
}
.swiper-centered.swiper-horizontal > .swiper-wrapper::before {
  height: 100%;
  min-height: 1px;
  width: var(--swiper-centered-offset-after);
}
.swiper-centered.swiper-vertical > .swiper-wrapper > .swiper-slide:first-child {
  margin-block-start: var(--swiper-centered-offset-before);
}
.swiper-centered.swiper-vertical > .swiper-wrapper::before {
  width: 100%;
  min-width: 1px;
  height: var(--swiper-centered-offset-after);
}
.swiper-centered > .swiper-wrapper > .swiper-slide {
  scroll-snap-align: center center;
}
.swiper-virtual .swiper-slide {
  -webkit-backface-visibility: hidden;
  transform: translateZ(0);
}
.swiper-virtual.swiper-css-mode .swiper-wrapper::after {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  pointer-events: none;
}
.swiper-virtual.swiper-css-mode.swiper-horizontal .swiper-wrapper::after {
  height: 1px;
  width: var(--swiper-virtual-size);
}
.swiper-virtual.swiper-css-mode.swiper-vertical .swiper-wrapper::after {
  width: 1px;
  height: var(--swiper-virtual-size);
}
:root {
  --swiper-navigation-size: 44px;
}
.swiper-button {
  position: absolute;
  left: 50%;
  margin-left: 40px;
  bottom: 24px;
  z-index: 1000;
  display: flex;
}
.swiper-button-stop {
  background-image: url(../../assets/img/slider_icon.svg) !important;
  background-position: -60px -70px;
  width: 16px;
  height: 16px;
  cursor: pointer;
}
.swiper-button-play {
  background-image: url(../../assets/img/slider_icon.svg) !important;
  background-position: -40px -70px;
  width: 16px;
  height: 16px;
  cursor: pointer;
}

.swiper-button-next,
.swiper-button-prev {
  position: absolute;
  top: 50%;
  width: calc(var(--swiper-navigation-size) / 44 * 27);
  height: var(--swiper-navigation-size);
  margin-top: calc(0px - (var(--swiper-navigation-size) / 2));
  z-index: 10;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--swiper-navigation-color, var(--swiper-theme-color));
}
.swiper-button-next.swiper-button-disabled,
.swiper-button-prev.swiper-button-disabled {
  opacity: 0.35;
  cursor: auto;
  pointer-events: none;
}
.swiper-button-next.swiper-button-hidden,
.swiper-button-prev.swiper-button-hidden {
  opacity: 0;
  cursor: auto;
  pointer-events: none;
}
.swiper-navigation-disabled .swiper-button-next,
.swiper-navigation-disabled .swiper-button-prev {
  display: none !important;
}
.swiper-button-next:after,
.swiper-button-prev:after {
  font-family: swiper-icons;
  font-size: var(--swiper-navigation-size);
  text-transform: none !important;
  letter-spacing: 0;
  font-variant: initial;
  line-height: 1;
}
.swiper-button-prev,
.swiper-rtl .swiper-button-next {
  left: 10px;
  right: auto;
}
.swiper-button-prev:after,
.swiper-rtl .swiper-button-next:after {
  content: "prev";
}
.swiper-button-next,
.swiper-rtl .swiper-button-prev {
  right: 10px;
  left: auto;
}
.swiper-button-next:after,
.swiper-rtl .swiper-button-prev:after {
  content: "next";
}
.swiper-button-lock {
  display: none;
}
.swiper-pagination {
  position: absolute;
  text-align: center;
  transition: 0.3s opacity;
  transform: translate3d(0, 0, 0);
  z-index: 10;
}
.swiper-pagination.swiper-pagination-hidden {
  opacity: 0;
}
.swiper-pagination-disabled > .swiper-pagination,
.swiper-pagination.swiper-pagination-disabled {
  display: none !important;
}
.swiper-horizontal > .swiper-pagination-bullets,
.swiper-pagination-bullets.swiper-pagination-horizontal,
.swiper-pagination-custom,
.swiper-pagination-fraction {
  bottom: 20px;
  left: 0;
  width: 100%;
}
.swiper-pagination-bullets-dynamic {
  overflow: hidden;
  font-size: 0;
}
.swiper-pagination-bullets-dynamic .swiper-pagination-bullet {
  transform: scale(0.33);
  position: relative;
}
.swiper-pagination-bullets-dynamic .swiper-pagination-bullet-active {
  transform: scale(1);
}
.swiper-pagination-bullets-dynamic .swiper-pagination-bullet-active-main {
  transform: scale(1);
}
.swiper-pagination-bullets-dynamic .swiper-pagination-bullet-active-prev {
  transform: scale(0.66);
}
.swiper-pagination-bullets-dynamic .swiper-pagination-bullet-active-prev-prev {
  transform: scale(0.33);
}
.swiper-pagination-bullets-dynamic .swiper-pagination-bullet-active-next {
  transform: scale(0.66);
}
.swiper-pagination-bullets-dynamic .swiper-pagination-bullet-active-next-next {
  transform: scale(0.33);
}
.swiper-pagination-bullet {
  width: var(
    --swiper-pagination-bullet-width,
    var(--swiper-pagination-bullet-size, 8px)
  );
  height: var(
    --swiper-pagination-bullet-height,
    var(--swiper-pagination-bullet-size, 8px)
  );
  display: inline-block;
  border-radius: 50%;
  background: var(--swiper-pagination-bullet-inactive-color, #000);
  opacity: var(--swiper-pagination-bullet-inactive-opacity, 0.2);
}
button.swiper-pagination-bullet {
  border: none;
  margin: 0;
  padding: 0;
  box-shadow: none;
  -webkit-appearance: none;
  appearance: none;
}
.swiper-pagination-clickable .swiper-pagination-bullet {
  cursor: pointer;
}
.swiper-pagination-bullet:only-child {
  display: none !important;
}
.swiper-pagination-bullet-active {
  opacity: var(--swiper-pagination-bullet-opacity, 1);
  background: var(--swiper-pagination-color, var(--swiper-theme-color));
}
.swiper-pagination-vertical.swiper-pagination-bullets,
.swiper-vertical > .swiper-pagination-bullets {
  right: 10px;
  top: 50%;
  transform: translate3d(0px, -50%, 0);
}
.swiper-pagination-vertical.swiper-pagination-bullets .swiper-pagination-bullet,
.swiper-vertical > .swiper-pagination-bullets .swiper-pagination-bullet {
  margin: var(--swiper-pagination-bullet-vertical-gap, 6px) 0;
  display: block;
}
.swiper-pagination-vertical.swiper-pagination-bullets.swiper-pagination-bullets-dynamic,
.swiper-vertical
  > .swiper-pagination-bullets.swiper-pagination-bullets-dynamic {
  top: 50%;
  transform: translateY(-50%);
  width: 8px;
}
.swiper-pagination-vertical.swiper-pagination-bullets.swiper-pagination-bullets-dynamic
  .swiper-pagination-bullet,
.swiper-vertical
  > .swiper-pagination-bullets.swiper-pagination-bullets-dynamic
  .swiper-pagination-bullet {
  display: inline-block;
  transition: 0.2s transform, 0.2s top;
}
.swiper-horizontal > .swiper-pagination-bullets .swiper-pagination-bullet,
.swiper-pagination-horizontal.swiper-pagination-bullets
  .swiper-pagination-bullet {
  margin: 0 var(--swiper-pagination-bullet-horizontal-gap, 4px);
}
.swiper-horizontal
  > .swiper-pagination-bullets.swiper-pagination-bullets-dynamic,
.swiper-pagination-horizontal.swiper-pagination-bullets.swiper-pagination-bullets-dynamic {
  left: 50%;
  transform: translateX(-50%);
  white-space: nowrap;
}
.swiper-horizontal
  > .swiper-pagination-bullets.swiper-pagination-bullets-dynamic
  .swiper-pagination-bullet,
.swiper-pagination-horizontal.swiper-pagination-bullets.swiper-pagination-bullets-dynamic
  .swiper-pagination-bullet {
  transition: 0.2s transform, 0.2s left;
}
.swiper-horizontal.swiper-rtl
  > .swiper-pagination-bullets-dynamic
  .swiper-pagination-bullet {
  transition: 0.2s transform, 0.2s right;
}
.swiper-pagination-progressbar {
  background: rgba(0, 0, 0, 0.25);
  position: absolute;
}
.swiper-pagination-progressbar .swiper-pagination-progressbar-fill {
  background: var(--swiper-pagination-color, var(--swiper-theme-color));
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  transform: scale(0);
  transform-origin: left top;
}
.swiper-rtl .swiper-pagination-progressbar .swiper-pagination-progressbar-fill {
  transform-origin: right top;
}
.swiper-horizontal > .swiper-pagination-progressbar,
.swiper-pagination-progressbar.swiper-pagination-horizontal,
.swiper-pagination-progressbar.swiper-pagination-vertical.swiper-pagination-progressbar-opposite,
.swiper-vertical
  > .swiper-pagination-progressbar.swiper-pagination-progressbar-opposite {
  width: 100%;
  height: 4px;
  left: 0;
  top: 0;
}
.swiper-horizontal
  > .swiper-pagination-progressbar.swiper-pagination-progressbar-opposite,
.swiper-pagination-progressbar.swiper-pagination-horizontal.swiper-pagination-progressbar-opposite,
.swiper-pagination-progressbar.swiper-pagination-vertical,
.swiper-vertical > .swiper-pagination-progressbar {
  width: 4px;
  height: 100%;
  left: 0;
  top: 0;
}
.swiper-pagination-lock {
  display: none;
}
.swiper-scrollbar {
  border-radius: 10px;
  position: relative;
  -ms-touch-action: none;
  background: rgba(0, 0, 0, 0.1);
}
.swiper-scrollbar-disabled > .swiper-scrollbar,
.swiper-scrollbar.swiper-scrollbar-disabled {
  display: none !important;
}
.swiper-horizontal > .swiper-scrollbar,
.swiper-scrollbar.swiper-scrollbar-horizontal {
  position: absolute;
  left: 1%;
  bottom: 3px;
  z-index: 50;
  height: 5px;
  width: 98%;
}
.swiper-scrollbar.swiper-scrollbar-vertical,
.swiper-vertical > .swiper-scrollbar {
  position: absolute;
  right: 3px;
  top: 1%;
  z-index: 50;
  width: 5px;
  height: 98%;
}
.swiper-scrollbar-drag {
  height: 100%;
  width: 100%;
  position: relative;
  background: rgba(0, 0, 0, 0.5);
  border-radius: 10px;
  left: 0;
  top: 0;
}
.swiper-scrollbar-cursor-drag {
  cursor: move;
}
.swiper-scrollbar-lock {
  display: none;
}
.swiper-zoom-container {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.swiper-zoom-container > canvas,
.swiper-zoom-container > img,
.swiper-zoom-container > svg {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}
.swiper-slide-zoomed {
  cursor: move;
}
.swiper-lazy-preloader {
  width: 42px;
  height: 42px;
  position: absolute;
  left: 50%;
  top: 50%;
  margin-left: -21px;
  margin-top: -21px;
  z-index: 10;
  transform-origin: 50%;
  box-sizing: border-box;
  border: 4px solid var(--swiper-preloader-color, var(--swiper-theme-color));
  border-radius: 50%;
  border-top-color: transparent;
}
.swiper-watch-progress .swiper-slide-visible .swiper-lazy-preloader,
.swiper:not(.swiper-watch-progress) .swiper-lazy-preloader {
  animation: swiper-preloader-spin 1s infinite linear;
}
.swiper-lazy-preloader-white {
  --swiper-preloader-color: #fff;
}
.swiper-lazy-preloader-black {
  --swiper-preloader-color: #000;
}
@keyframes swiper-preloader-spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
.swiper .swiper-notification {
  position: absolute;
  left: 0;
  top: 0;
  pointer-events: none;
  opacity: 0;
  z-index: -1000;
}
.swiper-free-mode > .swiper-wrapper {
  transition-timing-function: ease-out;
  margin: 0 auto;
}
.swiper-grid > .swiper-wrapper {
  flex-wrap: wrap;
}
.swiper-grid-column > .swiper-wrapper {
  flex-wrap: wrap;
  flex-direction: column;
}
.swiper-fade.swiper-free-mode .swiper-slide {
  transition-timing-function: ease-out;
}
.swiper-fade .swiper-slide {
  pointer-events: none;
  transition-property: opacity;
}
.swiper-fade .swiper-slide .swiper-slide {
  pointer-events: none;
}
.swiper-fade .swiper-slide-active,
.swiper-fade .swiper-slide-active .swiper-slide-active {
  pointer-events: auto;
}
.swiper-cube {
  overflow: visible;
}
.swiper-cube .swiper-slide {
  pointer-events: none;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  z-index: 1;
  visibility: hidden;
  transform-origin: 0 0;
  width: 100%;
  height: 100%;
}
.swiper-cube .swiper-slide .swiper-slide {
  pointer-events: none;
}
.swiper-cube.swiper-rtl .swiper-slide {
  transform-origin: 100% 0;
}
.swiper-cube .swiper-slide-active,
.swiper-cube .swiper-slide-active .swiper-slide-active {
  pointer-events: auto;
}
.swiper-cube .swiper-slide-active,
.swiper-cube .swiper-slide-next,
.swiper-cube .swiper-slide-next + .swiper-slide,
.swiper-cube .swiper-slide-prev {
  pointer-events: auto;
  visibility: visible;
}
.swiper-cube .swiper-slide-shadow-bottom,
.swiper-cube .swiper-slide-shadow-left,
.swiper-cube .swiper-slide-shadow-right,
.swiper-cube .swiper-slide-shadow-top {
  z-index: 0;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}
.swiper-cube .swiper-cube-shadow {
  position: absolute;
  left: 0;
  bottom: 0px;
  width: 100%;
  height: 100%;
  opacity: 0.6;
  z-index: 0;
}
.swiper-cube .swiper-cube-shadow:before {
  content: "";
  background: #000;
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  right: 0;
  filter: blur(50px);
}
.swiper-flip {
  overflow: visible;
}
.swiper-flip .swiper-slide {
  pointer-events: none;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  z-index: 1;
}
.swiper-flip .swiper-slide .swiper-slide {
  pointer-events: none;
}
.swiper-flip .swiper-slide-active,
.swiper-flip .swiper-slide-active .swiper-slide-active {
  pointer-events: auto;
}
.swiper-flip .swiper-slide-shadow-bottom,
.swiper-flip .swiper-slide-shadow-left,
.swiper-flip .swiper-slide-shadow-right,
.swiper-flip .swiper-slide-shadow-top {
  z-index: 0;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}
.swiper-creative .swiper-slide {
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  overflow: hidden;
  transition-property: transform, opacity, height;
}
.swiper-cards {
  overflow: visible;
}
.swiper-cards .swiper-slide {
  transform-origin: center bottom;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  overflow: hidden;
}
</style>