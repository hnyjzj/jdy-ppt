<template>
  <div class="jdy-logo" :class="{ compact }">
    <div class="logo-gem" aria-hidden="true">
      <span class="facet facet-a" />
      <span class="facet facet-b" />
      <span class="facet facet-c" />
    </div>
    <div v-if="!markOnly" class="logo-copy">
      <strong>金斗云</strong>
      <small>JEWELRY BUSINESS CLOUD</small>
    </div>
  </div>
</template>

<script setup lang="ts">
withDefaults(defineProps<{
  compact?: boolean
  markOnly?: boolean
}>(), {
  compact: false,
  markOnly: false,
})
</script>

<style scoped>
.jdy-logo {
  display: inline-flex;
  align-items: center;
  gap: 18px;
}

.logo-gem {
  position: relative;
  width: 72px;
  height: 72px;
  transform: rotate(45deg);
  border: 1px solid rgba(92, 237, 210, 0.7);
  border-radius: 16px;
  background: linear-gradient(145deg, rgba(76, 224, 198, 0.22), rgba(20, 91, 111, 0.12));
  box-shadow: 0 0 42px rgba(76, 224, 198, 0.22), inset 0 0 22px rgba(255, 255, 255, 0.05);
  overflow: hidden;
}

.facet {
  position: absolute;
  display: block;
  border: 1px solid rgba(241, 182, 111, 0.55);
}

.facet-a { inset: 12px; border-radius: 10px; }
.facet-b { width: 46px; height: 1px; left: 12px; top: 34px; transform: rotate(45deg); }
.facet-c { width: 46px; height: 1px; left: 12px; top: 34px; transform: rotate(-45deg); }

.logo-copy {
  display: grid;
  gap: 4px;
}

.logo-copy strong {
  font-size: 32px;
  line-height: 1;
  letter-spacing: 0.16em;
  color: #f7fbff;
}

.logo-copy small {
  font-size: 9px;
  letter-spacing: 0.2em;
  color: #7f9aae;
}

.compact .logo-gem { width: 42px; height: 42px; border-radius: 10px; }
.compact .facet-a { inset: 8px; border-radius: 7px; }
.compact .facet-b,
.compact .facet-c { width: 27px; left: 7px; top: 20px; }
.compact .logo-copy strong { font-size: 21px; }
.compact .logo-copy small { display: none; }
</style>
