<template>
  <div class="container mx-auto px-4 mt-4">
    <div class="relative ml-[234px] h-[460px] bg-gray-200 overflow-hidden">
      <!-- 轮播图容器 -->
      <div class="relative h-full">
        <div
          class="flex transition-transform duration-500 h-full"
          :style="{ transform: `translateX(-${currentSlide * 100}%)` }"
        >
          <div
            v-for="(slide, index) in slides"
            :key="index"
            class="min-w-full h-full relative"
          >
            <img :src="slide.image" :alt="slide.title" class="w-full h-full object-cover">
            <div class="absolute inset-0 flex flex-col justify-center pl-12 text-white">
              <h2 class="text-5xl font-bold mb-4" style="text-shadow: 2px 2px 4px rgba(0,0,0,0.3)">{{ slide.title }}</h2>
              <p class="text-xl mb-8" style="text-shadow: 1px 1px 2px rgba(0,0,0,0.3)">{{ slide.subtitle }}</p>
              <button class="bg-white text-gray-800 px-10 py-3 w-fit hover:bg-gray-100 transition-colors font-medium">
                立即查看
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- 左右箭头 -->
      <button
        @click="prevSlide"
        class="absolute left-4 top-1/2 -translate-y-1/2 bg-white/20 hover:bg-white/40 text-white p-2 transition-colors"
      >
        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
        </svg>
      </button>
      <button
        @click="nextSlide"
        class="absolute right-4 top-1/2 -translate-y-1/2 bg-white/20 hover:bg-white/40 text-white p-2 transition-colors"
      >
        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
        </svg>
      </button>

      <!-- 指示器 -->
      <div class="absolute bottom-6 left-1/2 -translate-x-1/2 flex gap-2">
        <button
          v-for="(slide, index) in slides"
          :key="index"
          @click="currentSlide = index"
          class="w-3 h-3 rounded-full transition-all"
          :class="currentSlide === index ? 'bg-white w-8' : 'bg-white/50'"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const currentSlide = ref(0)
let intervalId: number | null = null

const slides = [
  {
    title: 'REDMI Watch 6',
    subtitle: '轻薄长续航 大屏更出彩',
    image: 'https://ext.same-assets.com/2162967630/3050256334.webp'
  },
  {
    title: 'xiaomi 15 系列',
    subtitle: '骁龙8至尊版 徕卡光学Summilux镜头',
    image: 'https://ext.same-assets.com/2162967630/286153124.webp'
  },
  {
    title: 'REDMI K Pad',
    subtitle: '8.8" 3K LCD 超薄金属机身',
    image: 'https://ext.same-assets.com/2162967630/1586080159.webp'
  },
  {
    title: 'Xiaomi Watch S4',
    subtitle: '高精度健康监测 专业运动体验',
    image: 'https://ext.same-assets.com/2162967630/3283254465.webp'
  }
]

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length
}

const prevSlide = () => {
  currentSlide.value = currentSlide.value === 0 ? slides.length - 1 : currentSlide.value - 1
}

onMounted(() => {
  intervalId = window.setInterval(nextSlide, 5000)
})

onUnmounted(() => {
  if (intervalId) {
    clearInterval(intervalId)
  }
})
</script>
