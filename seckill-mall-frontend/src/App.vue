<script setup lang="ts">
import TopNavBar from './components/TopNavBar.vue'
import MainNavBar from './components/MainNavBar.vue'
import CategorySidebar from './components/CategorySidebar.vue'
import HeroSlider from './components/HeroSlider.vue'
import QuickLinks from './components/QuickLinks.vue'
import ProductSections from './components/ProductSections.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="min-h-screen bg-gray-50">
    <!-- 顶部导航栏 -->
    <TopNavBar />

    <!-- 主导航栏 -->
    <MainNavBar />

    <!-- 主内容区 -->
    <div class="relative">
      <!-- 左侧分类菜单 -->
      <CategorySidebar />

      <!-- 轮播图 -->
      <HeroSlider />

      <!-- 快捷入口 -->
      <QuickLinks />
    </div>

    <!-- 产品展示区域 -->
    <ProductSections />

    <!-- 页脚 -->
    <Footer />
  </div>
</template>

<style>
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}
</style>
