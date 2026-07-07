<script setup lang="ts">
import { ref, computed } from 'vue'

const patterns = ['YYYY-MM-DD', 'DD.MM.YYYY', 'DD MMMM YYYY', 'HH:mm']
const selected = ref(patterns[0])
const now = ref(new Date())

function format(date: Date, pattern: string): string {
  const pad = (n: number) => String(n).padStart(2, '0')
  const months = ['January','February','March','April','May','June',
    'July','August','September','October','November','December']
  return pattern
      .replace('YYYY', String(date.getFullYear()))
      .replace('MMMM', months[date.getMonth()])
      .replace('MM', pad(date.getMonth() + 1))
      .replace('DD', pad(date.getDate()))
      .replace('HH', pad(date.getHours()))
      .replace('mm', pad(date.getMinutes()))
}

const result = computed(() => format(now.value, selected.value))
</script>

<template>
  <div class="date-demo">
    <select v-model="selected">
      <option v-for="p in patterns" :key="p" :value="p">{{ p }}</option>
    </select>
    <p><code>formatDate(new Date(), '{{ selected }}')</code> → <strong>"{{ result }}"</strong></p>
  </div>
</template>

<style scoped>
.date-demo {
  border: 1px solid var(--vp-c-divider);
  border-radius: 12px;
  padding: 20px;
  margin: 24px 0;
  background: var(--vp-c-bg-soft);
}
.date-demo select {
  padding: 6px 12px;
  border-radius: 6px;
  border: 1px solid var(--vp-c-divider);
  background: var(--vp-c-bg);
  color: var(--vp-c-text-1);
  margin-bottom: 12px;
}
.date-demo strong {
  color: var(--vp-c-brand-1);
}
</style>