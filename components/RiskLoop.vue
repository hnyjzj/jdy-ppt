<template>
  <div class="risk-shell">
    <div class="risk-track" />
    <div v-for="(step, index) in steps" :key="step.title" class="risk-step">
      <div class="risk-icon" :class="`tone-${index}`">{{ step.mark }}</div>
      <span>{{ String(index + 1).padStart(2, '0') }}</span>
      <strong>{{ step.title }}</strong>
      <small>{{ step.desc }}</small>
      <i v-if="index < steps.length - 1">→</i>
    </div>
  </div>
</template>

<script setup lang="ts">
const steps = [
  { mark: '◉', title: '设备感知', desc: '摄像头 / 人脸设备' },
  { mark: '◇', title: '规则识别', desc: '客户 / 检查 / 离线' },
  { mark: '!', title: '实时触达', desc: 'PC / 企微 / 待办' },
  { mark: '✓', title: '分派处理', desc: '接单 / 转交 / 复核' },
  { mark: '⌁', title: '审计沉淀', desc: '证据 / 时间线 / 导出' },
]
</script>

<style scoped>
.risk-shell { position: relative; width: 100%; display: grid; grid-template-columns: repeat(5, 1fr); gap: 18px; padding: 30px 0 12px; }
.risk-track { position: absolute; left: 9%; right: 9%; top: 67px; height: 1px; background: linear-gradient(90deg, #4ce0c6, #f1b66f, #ff6b9a); opacity: .36; }
.risk-step { position: relative; display: flex; flex-direction: column; align-items: center; text-align: center; }
.risk-icon { width: 74px; height: 74px; display: grid; place-items: center; border-radius: 24px; font-size: 26px; color: #eafffb; background: #0b1f31; border: 1px solid rgba(255,255,255,.12); box-shadow: 0 18px 35px rgba(0,0,0,.25); z-index: 1; }
.tone-0, .tone-1 { border-color: rgba(76,224,198,.35); box-shadow: 0 18px 38px rgba(76,224,198,.08); }
.tone-2 { border-color: rgba(255,107,154,.5); box-shadow: 0 18px 38px rgba(255,107,154,.11); }
.tone-3, .tone-4 { border-color: rgba(241,182,111,.35); box-shadow: 0 18px 38px rgba(241,182,111,.08); }
.risk-step > span { margin-top: 15px; color: #506b7f; font-size: 9px; letter-spacing: .16em; }
.risk-step strong { margin-top: 4px; font-size: 15px; }
.risk-step small { margin-top: 5px; color: #7893a7; font-size: 10px; }
.risk-step i { position: absolute; right: -16px; top: 31px; color: #587386; font-style: normal; font-size: 16px; z-index: 2; }
</style>
