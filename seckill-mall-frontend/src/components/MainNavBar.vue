<template>
  <div class="bg-white border-b">
    <div class="container mx-auto px-4">
      <div class="flex items-center justify-between h-[100px]">
        <!-- Logo -->
        <div class="flex items-center">
          <a href="#" class="flex items-center">
            <img src="https://ext.same-assets.com/2162967630/1112254255.png" alt="小米" class="h-14">
          </a>
        </div>

        <!-- 主导航菜单 -->
        <nav class="flex items-center gap-8 text-sm">
          <div
            v-for="item in navItems"
            :key="item.name"
            class="relative group"
            @mouseenter="hoveredNav = item.name"
            @mouseleave="hoveredNav = null"
          >
            <a href="#" class="hover:text-orange-500">{{ item.name }}</a>

            <!-- 下拉菜单 -->
            <div
              v-if="item.children && hoveredNav === item.name"
              class="absolute top-full left-0 bg-white shadow-lg border mt-2 min-w-[200px] z-50"
            >
              <div class="py-2">
                <a
                  v-for="child in item.children"
                  :key="child"
                  href="#"
                  class="block px-6 py-2 hover:bg-gray-50 hover:text-orange-500"
                >
                  {{ child }}
                </a>
              </div>
            </div>
          </div>
        </nav>

        <!-- 搜索框 -->
        <div class="flex items-center gap-4">
          <div class="relative">
            <input
              type="text"
              placeholder="REDMI K90 Pro Max"
              class="w-[300px] px-4 py-2 border border-gray-300 rounded focus:outline-none focus:border-orange-500"
            >
            <button class="absolute right-0 top-0 h-full px-4 bg-white hover:text-orange-500">
              <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const hoveredNav = ref<string | null>(null)

const navItems = [
  {
    name: 'Xiaomi手机',
    children: ['Xiaomi 数字系列', 'Xiaomi MIX', 'Xiaomi Civi', 'REDMI K系列', 'REDMI Turbo', 'REDMI Note', 'REDMI 数字系列']
  },
  {
    name: 'REDMI手机',
    children: ['REDMI K系列', 'REDMI Note系列', 'REDMI 数字系列']
  },
  {
    name: '电视',
    children: ['小米电视S Pro Mini LED', '小米电视S Mini LED', 'REDMI电视', '巨省电Pro']
  },
  {
    name: '笔记本',
    children: ['REDMI Book 14', 'REDMI Book Pro 14', 'REDMI Book Pro 16']
  },
  {
    name: '平板',
    children: ['Xiaomi Pad', 'REDMI Pad']
  },
  {
    name: '家电',
    children: ['空调', '冰箱', '洗衣机', '电视', '净水器', '扫地机器人']
  },
  {
    name: '路由器',
    children: ['小米路由器', 'REDMI路由器']
  },
  {
    name: '服务中心'
  },
  {
    name: '社区'
  }
]
</script>
