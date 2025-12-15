<template>
  <div class="absolute left-0 top-0 w-[234px] bg-[#333333]/90 text-white z-40">
    <div
      v-for="(item, index) in categories"
      :key="index"
      class="group relative border-b border-white/10"
      @mouseenter="hoveredCategory = index"
      @mouseleave="hoveredCategory = null"
    >
      <div class="flex items-center justify-between px-6 py-4 hover:bg-white/5 cursor-pointer transition-colors">
        <span class="text-sm">{{ item.name }}</span>
        <svg class="w-4 h-4 opacity-60 group-hover:opacity-100 transition-opacity" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
        </svg>
      </div>

      <!-- 悬浮展开内容 -->
      <div
        v-if="hoveredCategory === index && item.subcategories"
        class="absolute left-full top-0 bg-white text-gray-800 shadow-2xl w-[600px] p-8 border-t-2 border-orange-500"
      >
        <div class="grid grid-cols-3 gap-x-8 gap-y-4">
          <div v-for="sub in item.subcategories" :key="sub" class="text-sm hover:text-orange-500 cursor-pointer transition-colors py-1">
            {{ sub }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const hoveredCategory = ref<number | null>(null)

const categories = [
  {
    name: '手机',
    subcategories: ['Xiaomi 15系列', 'REDMI K90 Pro Max', 'REDMI K90', 'Xiaomi 17 Pro Max', 'Xiaomi 17 Pro', 'Xiaomi 17']
  },
  {
    name: '电视',
    subcategories: ['小米电视S Pro', '小米电视S Mini LED', 'REDMI电视', '巨省电Pro']
  },
  {
    name: '家电',
    subcategories: ['空调', '冰箱', '洗衣机', '净水器', '扫地机器人', '吸尘器']
  },
  {
    name: '笔记本 平板 显示器',
    subcategories: ['REDMI Book 14', 'Xiaomi Pad 8 Pro', 'Xiaomi Pad 8', 'REDMI Pad 2']
  },
  {
    name: '耳机 音箱',
    subcategories: ['Xiaomi Buds 5 Pro', 'REDMI Buds 6 Pro', 'Xiaomi 开放式耳机 Pro', '小米智能音箱']
  },
  {
    name: '健康 儿童',
    subcategories: ['体重秤', '体脂秤', '跑步机', '儿童手表', '儿童滑板车']
  },
  {
    name: '生活 箱包',
    subcategories: ['双肩包', '旅行箱', '收纳袋', '运动鞋', '眼镜']
  },
  {
    name: '智能 路由器',
    subcategories: ['小米路由器', 'REDMI路由器', '摄像机', '智能门锁', '门铃']
  },
  {
    name: '电源 配件',
    subcategories: ['移动电源', '充电器', '数据线', '插排', '手机壳']
  }
]
</script>
