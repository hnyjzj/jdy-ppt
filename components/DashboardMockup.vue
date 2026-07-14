<template>
  <div class="dashboard">
    <aside>
      <JdyLogo compact />
      <nav>
        <div class="active"><span>⌁</span>经营概览</div>
        <div><span>◇</span>销售管理</div>
        <div><span>□</span>库存管理</div>
        <div><span>◎</span>客户管理</div>
        <div><span>△</span>智能风控</div>
      </nav>
      <div class="tenant-pill">零售业态 · 总部</div>
    </aside>
    <main>
      <header>
        <div><small>2026 / 07 / 14</small><strong>下午好，王店长</strong></div>
        <div class="header-actions"><span>待办 3</span><b>王</b></div>
      </header>
      <section class="metrics">
        <article><small>今日销售</small><strong>¥ 86,420</strong><i class="up">+12.8%</i></article>
        <article><small>待处理单据</small><strong>18</strong><i>4 类业务</i></article>
        <article><small>库存件数</small><strong>12,680</strong><i>2 个业态</i></article>
        <article><small>今日进店</small><strong>236</strong><i class="up">+8.1%</i></article>
      </section>
      <section class="content-grid">
        <article class="trend-card">
          <div class="card-head"><strong>近 7 日经营趋势</strong><span>销售额 ▾</span></div>
          <div class="chart">
            <span v-for="(bar, i) in bars" :key="i" :style="{ height: `${bar}%` }"><i /></span>
          </div>
          <div class="chart-axis"><span>一</span><span>二</span><span>三</span><span>四</span><span>五</span><span>六</span><span>日</span></div>
        </article>
        <article class="todo-card">
          <div class="card-head"><strong>我的待办</strong><span>全部 3</span></div>
          <div class="todo"><b class="pink" />调拨审批 <span>10:30</span></div>
          <div class="todo"><b class="gold" />维修取件 <span>11:15</span></div>
          <div class="todo"><b class="teal" />预警复核 <span>刚刚</span></div>
        </article>
        <article class="alert-card">
          <div class="alert-icon">!</div>
          <div><small>智能风控提醒</small><strong>VIP 客户已到店</strong><span>零售 1 店 · 正门设备</span></div>
          <button>查看</button>
        </article>
      </section>
    </main>
  </div>
</template>

<script setup lang="ts">
const bars = [42, 57, 49, 68, 72, 63, 86]
</script>

<style scoped>
.dashboard { width: 880px; height: 392px; margin: auto; display: grid; grid-template-columns: 168px 1fr; overflow: hidden; border-radius: 20px; background: #0b1826; border: 1px solid rgba(255,255,255,.1); box-shadow: 0 28px 90px rgba(0,0,0,.42); color: #eaf6ff; }
aside { padding: 20px 16px; background: linear-gradient(180deg, #0c1d2d, #08131f); display: flex; flex-direction: column; }
nav { display: grid; gap: 6px; margin-top: 28px; }
nav div { padding: 9px 10px; color: #7891a4; border-radius: 9px; font-size: 11px; display: flex; gap: 9px; align-items: center; }
nav div span { width: 17px; text-align: center; }
nav .active { color: #eafffb; background: linear-gradient(90deg, rgba(76,224,198,.2), rgba(76,224,198,.02)); box-shadow: inset 2px 0 #4ce0c6; }
.tenant-pill { margin-top: auto; padding: 8px; border: 1px solid rgba(241,182,111,.2); border-radius: 9px; color: #d9a86e; font-size: 9px; text-align: center; }
main { padding: 20px 22px; background: radial-gradient(circle at 100% 0, rgba(76,224,198,.07), transparent 36%); }
header { display: flex; align-items: center; justify-content: space-between; }
header div:first-child { display: grid; }
header small { color: #577287; font-size: 8px; letter-spacing: .14em; }
header strong { font-size: 17px; margin-top: 3px; }
.header-actions { display: flex; align-items: center; gap: 12px; color: #8ca4b5; font-size: 9px; }
.header-actions b { width: 25px; height: 25px; display: grid; place-items: center; border-radius: 50%; background: rgba(76,224,198,.16); color: #4ce0c6; }
.metrics { display: grid; grid-template-columns: repeat(4,1fr); gap: 9px; margin: 16px 0 10px; }
.metrics article { padding: 12px; border-radius: 11px; background: rgba(255,255,255,.035); border: 1px solid rgba(255,255,255,.07); display: grid; }
.metrics small { color: #7891a4; font-size: 8px; }
.metrics strong { font-size: 16px; margin: 5px 0 3px; }
.metrics i { font-style: normal; color: #607a8e; font-size: 8px; }
.metrics .up { color: #4ce0c6; }
.content-grid { display: grid; grid-template-columns: 1.55fr .9fr; grid-template-rows: 154px 56px; gap: 10px; }
.content-grid article { background: rgba(255,255,255,.035); border: 1px solid rgba(255,255,255,.07); border-radius: 12px; }
.trend-card { padding: 12px 14px; }
.card-head { display: flex; justify-content: space-between; align-items: center; }
.card-head strong { font-size: 10px; }
.card-head span { color: #607a8e; font-size: 8px; }
.chart { height: 88px; display: flex; gap: 15px; align-items: end; padding: 12px 10px 0; border-bottom: 1px solid rgba(255,255,255,.06); }
.chart > span { flex: 1; min-height: 10%; position: relative; border-radius: 4px 4px 0 0; background: linear-gradient(180deg, #4ce0c6, rgba(76,224,198,.12)); }
.chart > span i { position: absolute; left: 50%; top: -4px; width: 5px; height: 5px; transform: translateX(-50%); background: #f1b66f; border-radius: 50%; box-shadow: 0 0 10px #f1b66f; }
.chart-axis { display: flex; justify-content: space-around; color: #536d80; font-size: 7px; margin-top: 5px; }
.todo-card { grid-row: span 2; padding: 13px; }
.todo { display: grid; grid-template-columns: 8px 1fr auto; align-items: center; gap: 7px; padding: 15px 2px; border-bottom: 1px solid rgba(255,255,255,.055); font-size: 9px; }
.todo b { width: 6px; height: 6px; border-radius: 50%; }
.todo span { color: #536d80; }
.pink { background: #ff6b9a; box-shadow: 0 0 9px #ff6b9a; }
.gold { background: #f1b66f; box-shadow: 0 0 9px #f1b66f; }
.teal { background: #4ce0c6; box-shadow: 0 0 9px #4ce0c6; }
.alert-card { padding: 10px 12px; display: flex; align-items: center; gap: 10px; }
.alert-icon { width: 30px; height: 30px; display: grid; place-items: center; border-radius: 9px; background: rgba(255,107,154,.12); color: #ff6b9a; font-weight: 800; }
.alert-card > div:nth-child(2) { display: grid; }
.alert-card small { color: #ff8fb2; font-size: 7px; }
.alert-card strong { font-size: 10px; }
.alert-card span { color: #607a8e; font-size: 7px; }
.alert-card button { margin-left: auto; border: 0; border-radius: 8px; background: rgba(76,224,198,.14); color: #4ce0c6; font-size: 8px; padding: 7px 10px; }
</style>
