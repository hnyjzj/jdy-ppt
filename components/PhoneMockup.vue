<template>
  <div class="phone-stage">
    <div class="halo halo-a" /><div class="halo halo-b" />
    <div class="phone">
      <div class="notch" />
      <div class="phone-screen">
        <header><span>9:41</span><b>微信</b><i>•••</i></header>
        <section class="welcome">
          <small>XX 珠宝 · 会员中心</small>
          <strong>你好，张女士</strong>
          <span>VIP · 8,260 积分</span>
        </section>
        <section class="quick-grid">
          <div><b>⌁</b><span>我的订单</span></div>
          <div><b>◇</b><span>电子质保</span></div>
          <div><b>★</b><span>积分明细</span></div>
          <div><b>＋</b><span>售后服务</span></div>
        </section>
        <section class="order-card">
          <div><small>最近订单</small><span>查看全部 →</span></div>
          <strong>足金戒指 · 已完成</strong>
          <p>订单 XD0703001 · ¥6,120</p>
          <button>查看电子质保</button>
        </section>
        <nav><span>首页</span><span>服务</span><span>我的</span></nav>
      </div>
    </div>
    <div class="phone-caption left"><b>授权绑定</b><span>手机号 / 渠道身份</span></div>
    <div class="phone-caption right"><b>数据同源</b><span>订单 / 质保 / 积分</span></div>
  </div>
</template>

<style scoped>
.phone-stage { position: relative; height: 390px; display: grid; place-items: center; }
.halo { position: absolute; border-radius: 50%; filter: blur(1px); }
.halo-a { width: 330px; height: 330px; background: radial-gradient(circle, rgba(76,224,198,.14), transparent 68%); }
.halo-b { width: 250px; height: 250px; border: 1px solid rgba(241,182,111,.16); }
.phone { position: relative; width: 206px; height: 390px; padding: 7px; border-radius: 34px; background: linear-gradient(145deg, #384957, #0b1118 42%, #33414c); box-shadow: 0 34px 80px rgba(0,0,0,.48), inset 0 0 0 1px rgba(255,255,255,.13); z-index: 2; }
.notch { position: absolute; width: 70px; height: 19px; left: 50%; top: 9px; transform: translateX(-50%); background: #050a0e; border-radius: 0 0 13px 13px; z-index: 3; }
.phone-screen { height: 100%; overflow: hidden; border-radius: 28px; background: #f4f7f5; color: #102127; position: relative; }
.phone-screen header { height: 34px; padding: 10px 13px 0; display: flex; justify-content: space-between; font-size: 7px; }
.phone-screen header b { font-size: 9px; }
.phone-screen header i { font-style: normal; }
.welcome { margin: 0 9px; padding: 17px 14px; border-radius: 17px; background: linear-gradient(135deg, #102b32, #16414a); color: #ecfff9; display: grid; position: relative; overflow: hidden; }
.welcome::after { content: ''; position: absolute; right: -28px; top: -35px; width: 95px; height: 95px; transform: rotate(45deg); border: 1px solid rgba(241,182,111,.35); border-radius: 22px; }
.welcome small { font-size: 7px; opacity: .7; }
.welcome strong { font-size: 15px; margin: 5px 0 8px; }
.welcome span { color: #e7bc79; font-size: 8px; }
.quick-grid { display: grid; grid-template-columns: repeat(4,1fr); gap: 4px; margin: 13px 9px; }
.quick-grid div { display: grid; place-items: center; gap: 4px; }
.quick-grid b { width: 28px; height: 28px; display: grid; place-items: center; border-radius: 9px; background: #e4f5ef; color: #176a5d; font-size: 11px; }
.quick-grid span { font-size: 6px; }
.order-card { margin: 0 9px; padding: 12px; border-radius: 14px; background: white; box-shadow: 0 8px 28px rgba(18,55,61,.09); }
.order-card div { display: flex; justify-content: space-between; }
.order-card small { font-size: 7px; color: #65787d; }
.order-card div span { font-size: 6px; color: #1a8b78; }
.order-card strong { display: block; font-size: 10px; margin: 10px 0 3px; }
.order-card p { font-size: 7px; color: #789; margin: 0 0 8px; }
.order-card button { width: 100%; border: 0; border-radius: 8px; padding: 7px; background: #12343d; color: #f4d6a6; font-size: 7px; }
.phone-screen nav { position: absolute; left: 0; right: 0; bottom: 0; height: 36px; background: white; display: flex; justify-content: space-around; align-items: center; color: #789; font-size: 6px; border-top: 1px solid #edf1ef; }
.phone-screen nav span:first-child { color: #177966; font-weight: 700; }
.phone-caption { position: absolute; width: 145px; padding: 11px 13px; border-radius: 12px; background: rgba(9,27,42,.88); border: 1px solid rgba(255,255,255,.08); display: grid; z-index: 1; }
.phone-caption b { font-size: 12px; }
.phone-caption span { color: #728ea2; font-size: 9px; margin-top: 3px; }
.phone-caption.left { left: 60px; top: 95px; border-left: 2px solid #4ce0c6; }
.phone-caption.right { right: 55px; bottom: 82px; border-right: 2px solid #f1b66f; text-align: right; }
</style>
