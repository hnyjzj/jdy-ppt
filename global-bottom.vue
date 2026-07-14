<template>
  <div v-if="$nav.currentPage > 1" class="global-footer">
    <div class="footer-brand">
      <span class="footer-gem" />
      <span>金斗云 · 珠宝经营一体化</span>
    </div>
    <div class="footer-page">{{ String($nav.currentPage).padStart(2, '0') }}</div>
  </div>
</template>
