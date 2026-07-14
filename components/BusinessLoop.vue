<template>
  <div class="loop-shell">
    <svg class="loop-lines" viewBox="0 0 740 330" aria-hidden="true">
      <defs>
        <linearGradient id="loopGradient" x1="0" y1="0" x2="1" y2="1">
          <stop offset="0" stop-color="#4ce0c6" />
          <stop offset="1" stop-color="#f1b66f" />
        </linearGradient>
      </defs>
      <ellipse cx="370" cy="165" rx="278" ry="116" fill="none" stroke="url(#loopGradient)" stroke-width="1.5" stroke-dasharray="7 8" opacity=".58" />
      <path d="M90 170 C140 45, 275 20, 370 48 C520 10, 650 78, 653 165 C660 256, 520 318, 370 283 C230 319, 92 258, 90 170Z" fill="none" stroke="rgba(255,255,255,.08)" />
    </svg>
    <div class="loop-center">
      <div class="center-gem">JDY</div>
      <strong>统一经营数据</strong>
      <small>一条链 · 一个口径 · 全程可追溯</small>
    </div>
    <div v-for="(node, index) in nodes" :key="node.title" class="loop-node" :style="positions[index]">
      <span>{{ node.no }}</span>
      <div><strong>{{ node.title }}</strong><small>{{ node.desc }}</small></div>
    </div>
  </div>
</template>

<script setup lang="ts">
const nodes = [
  { no: '01', title: '采购入库', desc: '单品建档' },
  { no: '02', title: '库存流转', desc: '调拨 · 盘点' },
  { no: '03', title: '销售结算', desc: '订金 · 收支' },
  { no: '04', title: '客户沉淀', desc: '积分 · 质保' },
  { no: '05', title: '售后服务', desc: '维修 · 复购' },
  { no: '06', title: '经营风控', desc: '预警 · 审计' },
]

const positions = [
  { left: '32px', top: '56px' },
  { right: '40px', top: '52px' },
  { right: '4px', top: '164px' },
  { right: '94px', bottom: '18px' },
  { left: '100px', bottom: '18px' },
  { left: '0px', top: '166px' },
]
</script>

<style scoped>
.loop-shell { position: relative; width: 740px; height: 330px; margin: auto; }
.loop-lines { position: absolute; inset: 0; width: 100%; height: 100%; }
.loop-center { position: absolute; left: 50%; top: 50%; transform: translate(-50%, -50%); width: 260px; height: 150px; display: flex; flex-direction: column; align-items: center; justify-content: center; border-radius: 50%; background: radial-gradient(circle at 50% 35%, rgba(76,224,198,.22), rgba(8,24,39,.94) 67%); border: 1px solid rgba(76,224,198,.26); box-shadow: 0 0 70px rgba(76,224,198,.11); }
.center-gem { width: 48px; height: 48px; display: grid; place-items: center; transform: rotate(45deg); border: 1px solid #4ce0c6; border-radius: 12px; color: #f1b66f; font-size: 11px; margin-bottom: 11px; }
.center-gem::first-line { transform: rotate(-45deg); }
.loop-center strong { font-size: 18px; }
.loop-center small { color: #7591a4; margin-top: 4px; }
.loop-node { position: absolute; min-width: 174px; padding: 12px 14px; border-radius: 14px; background: rgba(10,28,44,.92); border: 1px solid rgba(255,255,255,.09); display: flex; align-items: center; gap: 11px; box-shadow: 0 12px 32px rgba(0,0,0,.2); }
.loop-node > span { color: #4ce0c6; font: 700 10px/1 ui-monospace, monospace; padding: 7px; border-radius: 8px; background: rgba(76,224,198,.1); }
.loop-node div { display: grid; }
.loop-node strong { font-size: 14px; }
.loop-node small { color: #7591a4; font-size: 10px; }
</style>
