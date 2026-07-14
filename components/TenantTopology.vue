<template>
  <div class="topology-shell">
    <div class="topology-head">
      <span class="mini-label">统一经营底座</span>
      <strong>平台</strong>
      <small>标准能力 · 安全边界 · 运维体系</small>
    </div>
    <div class="topology-line" />
    <div class="tenant-card">
      <div class="tenant-title">
        <span class="tenant-dot" />
        <div><strong>珠宝集团租户</strong><small>客户、积分、组织统一</small></div>
        <b>完全隔离</b>
      </div>
      <div class="format-grid">
        <div class="format retail">
          <span>零售业态</span>
          <small>直营网点 · 加盟门店</small>
        </div>
        <div class="format wholesale">
          <span>批发业态</span>
          <small>展厅 · 批发仓</small>
        </div>
      </div>
      <div class="org-path">
        <div><span>01</span>区域</div><i />
        <div><span>02</span>门店 / 仓库</div><i />
        <div><span>03</span>部门 / 岗位</div><i />
        <div><span>04</span>员工 / 角色</div>
      </div>
    </div>
    <div class="guardrail">
      <span>租户边界</span><span>业态上下文</span><span>组织数据范围</span><span>按钮权限</span>
    </div>
  </div>
</template>

<style scoped>
.topology-shell {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  color: #eef8ff;
}

.topology-head {
  width: 300px;
  padding: 14px 22px;
  text-align: center;
  border: 1px solid rgba(76, 224, 198, .42);
  border-radius: 18px;
  background: linear-gradient(160deg, rgba(76,224,198,.14), rgba(11,31,48,.8));
  box-shadow: 0 16px 50px rgba(0,0,0,.24);
}

.topology-head strong { display: block; font-size: 22px; margin: 3px 0; }
.topology-head small { color: #83a0b4; }
.mini-label { color: #4ce0c6; font-size: 10px; letter-spacing: .18em; }
.topology-line { width: 1px; height: 24px; background: linear-gradient(#4ce0c6, rgba(76,224,198,.12)); }

.tenant-card {
  width: 690px;
  border: 1px solid rgba(255,255,255,.1);
  border-radius: 22px;
  padding: 18px;
  background: rgba(8,24,39,.86);
  box-shadow: 0 22px 70px rgba(0,0,0,.26);
}

.tenant-title { display: flex; align-items: center; gap: 12px; }
.tenant-title div { display: grid; }
.tenant-title strong { font-size: 18px; }
.tenant-title small { color: #7f9aae; }
.tenant-title b { margin-left: auto; color: #f1b66f; font-size: 11px; border: 1px solid rgba(241,182,111,.35); padding: 5px 9px; border-radius: 99px; }
.tenant-dot { width: 12px; height: 12px; border-radius: 50%; background: #4ce0c6; box-shadow: 0 0 18px #4ce0c6; }

.format-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin: 15px 0; }
.format { padding: 11px 14px; border-radius: 12px; display: flex; justify-content: space-between; align-items: center; }
.format span { font-weight: 700; }
.format small { opacity: .68; }
.retail { background: linear-gradient(90deg, rgba(76,224,198,.2), rgba(76,224,198,.05)); border-left: 3px solid #4ce0c6; }
.wholesale { background: linear-gradient(90deg, rgba(241,182,111,.2), rgba(241,182,111,.05)); border-left: 3px solid #f1b66f; }

.org-path { display: grid; grid-template-columns: 1fr 28px 1.25fr 28px 1.25fr 28px 1fr; align-items: center; }
.org-path div { padding: 10px; text-align: center; background: rgba(255,255,255,.04); border-radius: 10px; font-size: 12px; }
.org-path span { display: block; color: #607a8e; font-size: 9px; }
.org-path i { height: 1px; background: rgba(255,255,255,.18); position: relative; }
.org-path i::after { content: ''; position: absolute; right: -1px; top: -2px; border-left: 4px solid #607a8e; border-top: 2px solid transparent; border-bottom: 2px solid transparent; }
.guardrail { display: grid; grid-template-columns: repeat(4, 1fr); gap: 8px; width: 650px; margin-top: 10px; }
.guardrail span { text-align: center; font-size: 10px; color: #89a3b6; padding: 5px; border-top: 1px solid rgba(255,107,154,.36); }
</style>
