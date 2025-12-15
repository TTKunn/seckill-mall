<template>
  <div class="bg-gray-50 py-12">
    <!-- 手机分类 -->
    <ProductCategory
      title="手机"
      :products="phoneProducts"
      :promo-image="{ image: 'https://ext.same-assets.com/2162967630/3706049941.png', title: 'Xiaomi 15 系列' }"
    />

    <!-- 智能穿戴 -->
    <ProductCategory
      title="智能穿戴"
      :tabs="['耳机', '穿戴']"
      :products="wearableProducts"
      :promo-image="{ image: 'https://ext.same-assets.com/2162967630/3050256334.webp', title: 'REDMI Watch 6' }"
    />

    <!-- 笔记本 | 平板 -->
    <ProductCategory
      title="笔记本 | 平板"
      :tabs="['热门']"
      :products="computerProducts"
      :promo-image="{ image: 'https://ext.same-assets.com/2162967630/1172277931.webp', title: 'REDMI Pad 2' }"
    />

    <!-- 家电 -->
    <ProductCategory
      title="家电"
      :tabs="['热门', '电视影音', '空调']"
      :products="applianceProducts"
      :promo-image="{ image: 'https://ext.same-assets.com/2162967630/286153124.webp', title: '小米电视S系列' }"
    />

    <!-- 生活电器 -->
    <ProductCategory
      title="生活电器"
      :tabs="['电暖器', '扫地机', '空净', '清洁', '环境']"
      :products="homeProducts"
      :promo-image="{ image: 'https://ext.same-assets.com/2162967630/2238170876.webp', title: '米家扫地机器人 5' }"
    />

    <!-- 厨房电器 -->
    <ProductCategory
      title="厨房电器"
      :tabs="['净水器', '烟灶', '电饭煲', '微蒸烤']"
      :products="kitchenProducts"
      :promo-image="{ image: 'https://ext.same-assets.com/2162967630/3283254465.webp', title: '米素净水器1200G Pro' }"
    />

    <!-- 智能家居 -->
    <ProductCategory
      title="智能家居"
      :tabs="['小爱音箱', '门锁门铃', '路由器', '智能设备']"
      :products="smartHomeProducts"
      :promo-image="{ image: 'https://ext.same-assets.com/2162967630/2040252032.webp', title: 'Xiaomi Sound' }"
    />
  </div>
</template>

<script setup lang="ts">
import ProductCategory from './ProductCategory.vue'

const phoneProducts = [
  {
    image: 'https://ext.same-assets.com/2162967630/3706049941.png',
    name: 'REDMI K90 Pro Max',
    desc: '骁龙8至尊版 徕卡影像系统 | 5400mAh大电池',
    price: '3999元起'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/2917843981.png',
    name: 'REDMI K90',
    desc: '骁龙8至尊版 | 5000mAh | Boos音效',
    price: '2599元起'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/3125259371.png',
    name: 'Xiaomi 17 Pro Max',
    desc: '骁龙8至尊版大核 | 徕卡光学Summilux镜头 | 6.8寸',
    price: '5999元起'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/1787962666.png',
    name: 'Xiaomi 17 Pro',
    desc: '骁龙8至尊版大核 | 徕卡光学全焦段 | 骁龙8至尊版',
    price: '4999元起'
  }
]

const wearableProducts = [
  {
    image: 'https://ext.same-assets.com/2162967630/2844564514.png',
    name: 'Xiaomi 开放式耳机 Pro',
    desc: '人体工学设计 | 三点支撑 | 舒适不挤压',
    price: '999元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/536023697.webp',
    name: 'Xiaomi Buds 5 Pro',
    desc: '小米音频旗舰芯片 | 55dB深度降噪',
    price: '1199元',
    oldPrice: '1499元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/1586080159.webp',
    name: 'REDMI Buds 6 Pro',
    desc: '小米音频旗舰芯片 | 55dB深度降噪 | 大动圈',
    price: '369元',
    oldPrice: '699元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/2650640060.webp',
    name: 'Redmi Buds 6 青春版',
    desc: '42dB混合主动降噪 | 双设备切换风格',
    price: '139元'
  }
]

const computerProducts = [
  {
    image: 'https://ext.same-assets.com/2162967630/695852025.webp',
    name: 'Xiaomi Pad 8 Pro',
    desc: '骁龙8至尊版旗舰神U | 11.2英寸144Hz高刷',
    price: '2899元起'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/4148874726.webp',
    name: 'Xiaomi Pad 8',
    desc: '青年优选旗舰 | 5mAh超大电池 | 11.2英寸十点',
    price: '2299元起'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/2520673858.webp',
    name: 'REDMI Pad 2',
    desc: '2.5K超清护眼屏 | 9000mAh大电池 | 长续航',
    price: '1199元起'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/1458748060.webp',
    name: 'REDMI K Pad',
    desc: '8.8" 3K LCD 超薄金属机身 | 支持240Hz高',
    price: '2499元起',
    oldPrice: '2799元'
  }
]

const applianceProducts = [
  {
    image: 'https://ext.same-assets.com/2162967630/286153124.webp',
    name: '小米电视S Pro Mini LED系列',
    desc: '288分区全阵列 | 4,400nits峰值亮度',
    price: '4999元起'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/536023697.webp',
    name: '小米电视 S Mini LED 系列',
    desc: 'Mini LED 高分区技术 | 120Hz高刷',
    price: '2999元起'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/1586080159.webp',
    name: 'Redmi 智能电视 X 2025款',
    desc: '2.4K高色域屏幕 | 金属全面屏',
    price: '3499元起'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/2650640060.webp',
    name: '巨省电Pro 1.5匹超一级能效 米',
    desc: '超一级能效 | 直流变频 | 智能除湿',
    price: '2499元',
    oldPrice: '2999元'
  }
]

const homeProducts = [
  {
    image: 'https://ext.same-assets.com/2162967630/762757754.webp',
    name: '米家石墨烯风机',
    desc: '2000W功率 | 四维转风模式 | 石墨烯发热',
    price: '299元',
    oldPrice: '349元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/1044399105.webp',
    name: '米家石墨烯踢脚线电暖器 2',
    desc: '石墨烯发热 | 2200W双区调温 | IPX4防水',
    price: '387元',
    oldPrice: '449元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/1574472508.webp',
    name: '米家石墨烯智能电暖器',
    desc: '石墨烯发热 | 防止烫伤 | 独立区域加热',
    price: '516元',
    oldPrice: '549元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/3606954851.webp',
    name: '米家石墨烯油汀取暖器',
    desc: '超宽石墨烯出口 | 静音不干燥',
    price: '646元',
    oldPrice: '699元'
  }
]

const kitchenProducts = [
  {
    image: 'https://ext.same-assets.com/2162967630/3137088446.webp',
    name: '米家前置过滤器',
    desc: '虹吸排污 | 40μm精度过滤',
    price: '411元',
    oldPrice: '499元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/2743794963.webp',
    name: '米家即热饮水机',
    desc: '小体量设计 | 10档温度可调',
    price: '1099元',
    oldPrice: '1499元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/720014972.webp',
    name: '米家即热净水器Q1000',
    desc: '2倍出水速度 | RO反渗透过滤 | 超薄设计',
    price: '2799元',
    oldPrice: '3499元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/1056698333.webp',
    name: '米家净水器1000G',
    desc: '过滤精度0.0001μm | 1000加仑大通量',
    price: '1599元',
    oldPrice: '1999元'
  }
]

const smartHomeProducts = [
  {
    image: 'https://ext.same-assets.com/2162967630/1104039287.webp',
    name: 'Xiaomi 智能音箱 Pro',
    desc: '语音遥控器 | 一句话遥控家电 | 360度音',
    price: '299元',
    oldPrice: '369元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/596885234.webp',
    name: 'Xiaomi 智能音箱',
    desc: '对话AI音箱 | 问答聊天 | 百科问答',
    price: '199元',
    oldPrice: '249元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/2552761582.webp',
    name: 'Xiaomi智能家庭屏Pro 8',
    desc: 'MIUI Home智能中枢 | 7500mAh超长续航',
    price: '699元',
    oldPrice: '799元'
  },
  {
    image: 'https://ext.same-assets.com/2162967630/2607976118.webp',
    name: 'Xiaomi智能家庭屏 10',
    desc: 'MIUI Home | 10.1" 高清大屏 | 115度超广',
    price: '899元',
    oldPrice: '999元'
  }
]
</script>
