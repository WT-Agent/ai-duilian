<template>
  <div class="glass-card ticker-card">
    <div class="ticker-wrapper">
      <div v-for="(item, index) in tickerItems" :key="index" class="ticker-item">
        <span>{{ item.text }}</span>
        <span style="color: var(--success-color); font-weight: bold;">[楹联创作完成]</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tickerItems = ref([
  { text: '用户 138****5821 成功生成了龙年新春大吉七言楹联与横批“紫气东来”' },
  { text: '用户 177****9201 成功为科技公司开业拟定九言商业吉联与平仄校核' },
  { text: '用户 189****4190 成功创作了百年好合婚嫁对联与意境典故赏析' },
  { text: '用户 131****6632 成功生成了书房修身养性五言自勉联与平水韵校验' },
  { text: '用户 156****7739 成功拟定了名胜古迹观景楼台长联与对仗音律分析' },
]);
</script>
