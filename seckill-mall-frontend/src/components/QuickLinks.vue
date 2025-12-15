<template>
  <div class="container mx-auto px-4 mt-4">
    <div class="ml-[234px] grid grid-cols-6 gap-4">
      <div
        v-for="link in quickLinks"
        :key="link.name"
        class="bg-white p-6 flex flex-col items-center justify-center hover:shadow-lg cursor-pointer transition-shadow"
      >
        <div class="w-16 h-16 mb-3 flex items-center justify-center">
          <img :src="link.icon" :alt="link.name" class="w-full h-full object-contain">
        </div>
        <span class="text-sm text-gray-700">{{ link.name }}</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const quickLinks = [
  { name: '保障服务', icon: 'https://ext.same-assets.com/2162967630/2542959307.png' },
  { name: '企业团购', icon: 'https://ext.same-assets.com/2162967630/2236354308.png' },
  { name: 'F码通道', icon: 'https://ext.same-assets.com/2162967630/4140795453.png' },
  { name: '米粉卡', icon: 'https://ext.same-assets.com/2162967630/773189253.png' },
  { name: '以旧换新', icon: 'https://ext.same-assets.com/2162967630/1704593115.jpeg' },
  { name: '话费充值', icon: 'https://ext.same-assets.com/2162967630/1277369948.png' }
]
</script>
