<template>
  <section class="nomads-showcase-section">
    <div class="showcase-header">
      <div class="header-left">
        <h2 class="showcase-title">楹联创作与对仗押韵实战模板库</h2>
        <p class="showcase-subtitle">精选节日新春、商业开业、婚嫁寿诞与书房自勉对联，点击“一键套用”快速创作</p>
      </div>
      <span class="showcase-badge">已收录 {{ showcaseItems.length }} 个楹联精选模板</span>
    </div>

    <div class="showcase-grid">
      <div 
        v-for="item in showcaseItems" 
        :key="item.id" 
        class="glass-card showcase-card"
      >
        <div class="card-header">
          <span class="scenario-tag">{{ item.tag }}</span>
          <span class="usage-count">{{ item.usageCount }} 次应用</span>
        </div>

        <div class="card-content">
          <h3 class="item-title">{{ item.title }}</h3>
          <p class="item-prompt">“{{ item.prompt }}”</p>
        </div>

        <div class="card-action">
          <button class="apply-btn" @click="applyTemplate(item)">
            <span>一键套用</span>
            <svg class="arrow-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <line x1="5" y1="12" x2="19" y2="12"></line>
              <polyline points="12 5 19 12 12 19"></polyline>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed } from 'vue';

const emit = defineEmits<{
  (e: 'apply-template', payload: { prompt: string; duilianType?: string; length?: string; style?: string }): void;
}>();

export interface ShowcaseItem {
  id: string;
  tag: string;
  title: string;
  prompt: string;
  duilianType?: string;
  length?: string;
  style?: string;
  usageCount: string;
}

const showcaseItems = computed<ShowcaseItem[]>(() => [
  {
    id: 'duilian-1',
    tag: '新春贺岁',
    title: '龙年新春大吉七言喜庆楹联',
    prompt: '为家庭客厅大门创作一套龙年新春七言喜庆楹联，包含上联、下联与四字横批，表达辞旧迎新、阖家安康、事业蒸蒸日上的吉祥寓意。',
    duilianType: '新春贺岁与节日楹联',
    length: '七言联',
    style: '通俗喜庆',
    usageCount: '58.9k'
  },
  {
    id: 'duilian-2',
    tag: '商业开业',
    title: '科技公司开业大吉九言商业吉联',
    prompt: '为人工智能高科技公司开业拟定九言商业大吉联，融入创新突破、智启未来、商路广进的宏大意境，附平仄与词性对仗分析。',
    duilianType: '行业开业与商业吉联',
    length: '九言联',
    style: '气势磅礴',
    usageCount: '46.2k'
  },
  {
    id: 'duilian-3',
    tag: '婚嫁百年',
    title: '婚嫁喜庆百年好合典雅古风对联',
    prompt: '为一对热爱传统文化的新人撰写百年好合喜庆对联，要求词藻典雅古风、上仄下平合律，附典故成语赏析与横批。',
    duilianType: '婚嫁喜庆与寿诞对联',
    length: '七言联',
    style: '典雅古风',
    usageCount: '39.8k'
  },
  {
    id: 'duilian-4',
    tag: '书房自勉',
    title: '书房修身养性五言自勉联',
    prompt: '为个人书房撰写五言修身养性自勉联，体现淡泊明志、潜心学问、静以修身的高雅情调，附平水韵平仄校验。',
    duilianType: '名胜古迹与书房自勉联',
    length: '五言联',
    style: '清丽婉约',
    usageCount: '34.5k'
  },
  {
    id: 'duilian-5',
    tag: '名胜长联',
    title: '名胜古迹观景楼台登高抒怀长联',
    prompt: '为江南水乡古镇观景楼阁创作一套写景抒怀长联，融入四季风光与人文历史韵味，附对仗音律与适用悬挂场景指导。',
    duilianType: '名胜古迹与书房自勉联',
    length: '长联',
    style: '典雅古风',
    usageCount: '29.1k'
  },
  {
    id: 'duilian-6',
    tag: '寿诞祝寿',
    title: '八十大寿松柏长青尊亲祝寿联',
    prompt: '为老父亲八十大寿拟定祝寿楹联，表达福如东海、寿比南山、松柏长青的深厚情谊，要求文采典雅、意境深远。',
    duilianType: '婚嫁喜庆与寿诞对联',
    length: '七言联',
    style: '典雅古风',
    usageCount: '27.4k'
  }
]);

function applyTemplate(item: ShowcaseItem) {
  emit('apply-template', {
    prompt: item.prompt,
    duilianType: item.duilianType,
    length: item.length,
    style: item.style
  });
}
</script>

<style scoped>
.nomads-showcase-section {
  margin-top: 2rem;
  width: 100%;
}

.showcase-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  margin-bottom: 1.25rem;
  padding-bottom: 0.75rem;
  border-bottom: 1px solid var(--card-border);
}

.showcase-title {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--text-primary);
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.showcase-subtitle {
  font-size: 0.825rem;
  color: var(--text-secondary);
  margin-top: 0.25rem;
}

.showcase-badge {
  font-size: 0.75rem;
  color: #a5b4fc;
  background: rgba(99, 102, 241, 0.12);
  border: 1px solid rgba(99, 102, 241, 0.25);
  padding: 4px 10px;
  border-radius: 20px;
}

.showcase-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 1.25rem;
}

@media (min-width: 640px) {
  .showcase-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .showcase-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.showcase-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  padding: 1.25rem;
  background: rgba(255, 255, 255, 0.02);
  border: 1px solid var(--card-border);
  border-radius: 14px;
  transition: all 0.25s ease;
}

.showcase-card:hover {
  background: rgba(255, 255, 255, 0.05);
  border-color: rgba(99, 102, 241, 0.4);
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.75rem;
}

.scenario-tag {
  font-size: 0.75rem;
  font-weight: 600;
  padding: 3px 8px;
  border-radius: 6px;
  background: rgba(168, 85, 247, 0.15);
  color: #c084fc;
  border: 1px solid rgba(168, 85, 247, 0.3);
}

.usage-count {
  font-size: 0.75rem;
  color: var(--text-secondary);
}

.card-content {
  margin-bottom: 1rem;
  flex: 1;
}

.item-title {
  font-size: 0.95rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 0.4rem;
}

.item-prompt {
  font-size: 0.825rem;
  color: var(--text-secondary);
  line-height: 1.45;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  font-style: italic;
}

.card-action {
  padding-top: 0.75rem;
  border-top: 1px solid rgba(255, 255, 255, 0.04);
}

.apply-btn {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  padding: 0.5rem 1rem;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.3);
  border-radius: 8px;
  color: #a5b4fc;
  font-size: 0.825rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
}

.showcase-card:hover .apply-btn {
  background: var(--primary-gradient);
  border-color: transparent;
  color: white;
}

.arrow-icon {
  width: 14px;
  height: 14px;
  transition: transform 0.2s ease;
}

.apply-btn:hover .arrow-icon {
  transform: translateX(3px);
}
</style>
