<template>
  <button class="lang-toggle" @click="toggleLocale" :title="$t('lang.toggle')">
    {{ $t('lang.toggle') }}
  </button>
</template>

<script setup>
import { useI18n } from 'vue-i18n'

const { locale } = useI18n()

const toggleLocale = () => {
  const next = locale.value === 'en' ? 'zh' : 'en'
  locale.value = next
  localStorage.setItem('mirofish-locale', next)
}
</script>

<style scoped>
.lang-toggle {
  background: transparent;
  border: 1px solid currentColor;
  color: inherit;
  padding: 4px 10px;
  font-size: 11px;
  font-family: 'JetBrains Mono', monospace;
  font-weight: 600;
  cursor: pointer;
  border-radius: 3px;
  letter-spacing: 0.5px;
  transition: all 0.2s;
  opacity: 0.7;
}
.lang-toggle:hover {
  opacity: 1;
}
</style>
