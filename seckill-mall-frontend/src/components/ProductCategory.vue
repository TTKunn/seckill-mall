<template>
  <div class="container mx-auto px-4 mb-12">
    <!-- 分类标题和标签 -->
    <div class="flex items-center justify-between mb-6">
      <h2 class="text-2xl font-normal">{{ title }}</h2>
      <div class="flex items-center gap-6">
        <button
          v-for="tab in tabs"
          :key="tab"
          class="text-sm hover:text-orange-500 transition-colors"
        >
          {{ tab }}
        </button>
        <button class="flex items-center gap-2 text-sm text-gray-500 hover:text-orange-500 transition-colors group">
          <span>浏览更多</span>
          <svg class="w-5 h-5 bg-orange-500 text-white rounded-full p-1 group-hover:scale-110 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
          </svg>
        </button>
      </div>
    </div>

    <!-- 产品网格 -->
    <div class="flex gap-4">
      <!-- 左侧推广图 -->
      <div v-if="promoImage" class="flex-shrink-0 w-[234px] h-[614px] bg-white group hover:shadow-2xl transition-all duration-300 cursor-pointer overflow-hidden">
        <img :src="promoImage.image" :alt="promoImage.title" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
      </div>

      <!-- 产品列表 -->
      <div class="flex-1 grid grid-cols-4 gap-4">
        <div
          v-for="(product, index) in products"
          :key="index"
          class="bg-white group hover:shadow-2xl transition-all duration-300 cursor-pointer"
        >
          <div class="p-6">
            <!-- 产品图片 -->
            <div class="mb-4 h-[200px] flex items-center justify-center overflow-hidden">
              <img
                :src="product.image"
                :alt="product.name"
                class="max-w-full max-h-full object-contain group-hover:scale-110 transition-transform duration-300"
              >
            </div>

            <!-- 产品信息 -->
            <h3 class="text-base font-medium mb-2 group-hover:text-orange-500 transition-colors">{{ product.name }}</h3>
            <p class="text-sm text-gray-500 mb-3 line-clamp-2 h-10">{{ product.desc }}</p>

            <!-- 价格 -->
            <div class="flex items-center gap-2">
              <span class="text-orange-500 font-medium text-lg">{{ product.price }}</span>
              <span v-if="product.oldPrice" class="text-sm text-gray-400 line-through">{{ product.oldPrice }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Product {
  image: string
  name: string
  desc: string
  price: string
  oldPrice?: string
}

interface PromoImage {
  image: string
  title: string
}

defineProps<{
  title: string
  tabs?: string[]
  products: Product[]
  promoImage?: PromoImage
}>()
</script>
