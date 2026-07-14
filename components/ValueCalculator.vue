<template>
  <div class="calculator">
    <section class="controls">
      <div class="calc-title"><span>LIVE</span><strong>客户价值演算</strong><small>拖动参数，现场估算</small></div>
      <label>
        <div><span>门店数量</span><b>{{ stores }} 家</b></div>
        <input v-model.number="stores" type="range" min="1" max="100" step="1">
      </label>
      <label>
        <div><span>单店月均业务单</span><b>{{ tickets.toLocaleString('zh-CN') }} 笔</b></div>
        <input v-model.number="tickets" type="range" min="100" max="5000" step="100">
      </label>
      <label>
        <div><span>每单减少重复操作</span><b>{{ minutes }} 分钟</b></div>
        <input v-model.number="minutes" type="range" min="0.5" max="8" step="0.5">
      </label>
      <p>示意模型：门店数 × 月业务单量 × 每单节省时间。结果用于需求讨论，不构成收益承诺。</p>
    </section>
    <section class="results">
      <div class="result-main">
        <small>预计每月可释放业务时间</small>
        <strong>{{ monthlyHours.toLocaleString('zh-CN') }}</strong>
        <span>小时 / 月</span>
      </div>
      <div class="result-grid">
        <article><small>全年可释放</small><b>{{ annualHours.toLocaleString('zh-CN') }} 小时</b></article>
        <article><small>覆盖业务单</small><b>{{ monthlyTickets.toLocaleString('zh-CN') }} 笔 / 月</b></article>
      </div>
      <div class="value-path"><span>少重复录入</span><i>→</i><span>快业务协同</span><i>→</i><span>多经营洞察</span></div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue'

const stores = ref(12)
const tickets = ref(1200)
const minutes = ref(2)

const monthlyTickets = computed(() => stores.value * tickets.value)
const monthlyHours = computed(() => Math.round(monthlyTickets.value * minutes.value / 60))
const annualHours = computed(() => monthlyHours.value * 12)
</script>

<style scoped>
.calculator { display: grid; grid-template-columns: 1fr 1.05fr; gap: 22px; min-height: 340px; }
.controls, .results { border-radius: 22px; border: 1px solid rgba(255,255,255,.09); background: rgba(8,24,39,.78); padding: 22px; }
.calc-title { display: grid; grid-template-columns: auto 1fr auto; align-items: center; gap: 9px; margin-bottom: 19px; }
.calc-title > span { font-size: 8px; letter-spacing: .13em; padding: 5px 7px; border-radius: 99px; color: #081822; background: #4ce0c6; font-weight: 800; }
.calc-title strong { font-size: 17px; }
.calc-title small { color: #68869a; font-size: 9px; }
label { display: block; margin: 16px 0; }
label div { display: flex; justify-content: space-between; font-size: 11px; }
label div span { color: #9ab0c0; }
label b { color: #f0c28a; }
input[type='range'] { width: 100%; accent-color: #4ce0c6; margin-top: 8px; height: 4px; }
.controls p { margin: 18px 0 0; color: #5f7b8f; font-size: 9px; line-height: 1.6; }
.results { display: flex; flex-direction: column; justify-content: center; background: radial-gradient(circle at 50% 40%, rgba(76,224,198,.13), transparent 58%), rgba(8,24,39,.78); }
.result-main { text-align: center; display: grid; justify-items: center; }
.result-main small { color: #86a1b4; font-size: 10px; letter-spacing: .08em; }
.result-main strong { font-size: 66px; line-height: 1.04; margin: 7px 0 2px; background: linear-gradient(110deg, #f8fbff, #4ce0c6 52%, #f1b66f); -webkit-background-clip: text; color: transparent; }
.result-main span { color: #f1b66f; font-size: 11px; }
.result-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin: 22px 0; }
.result-grid article { padding: 12px; border-radius: 12px; background: rgba(255,255,255,.04); display: grid; text-align: center; }
.result-grid small { color: #68869a; font-size: 8px; }
.result-grid b { font-size: 12px; margin-top: 4px; }
.value-path { display: flex; justify-content: center; align-items: center; gap: 11px; color: #8ea7b8; font-size: 9px; }
.value-path i { color: #4ce0c6; font-style: normal; }
</style>
