<template>
  <div class="vp-card vp-learning-material">
    <div v-if="loading" class="star-tip-text" style="text-align:center;">正在检查 GitHub Star 状态...</div>
    <template v-else>
      <template v-if="isStar">
        <p class="star-success">✅ 感谢你的 Star！</p>
        <a :href="materialUrl" target="_blank" class="star-link">点击跳转部署配置</a>
      </template>
      <template v-else>
        <p class="star-tip-text">
          <span class="star-highlight">获取部署配置</span>
        </p>
        <button v-if="!starClicked" @click="goToStar" class="star-btn vp-btn">
          <svg class="github-icon" viewBox="0 0 16 16" width="18" height="18" fill="currentColor" style="vertical-align:middle;margin-right:6px;"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.19 0 .21.15.46.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"></path></svg>
          需要免费的star
        </button>
        <button v-else @click="fakeCheckStar" class="star-btn star-check vp-btn">我已经star</button>
      </template>
    </template>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const loading = ref(false)
const isStar = ref(false)
const starClicked = ref(false)
const repoUrl = 'https://github.com/ChainXi/ChainXi-Admin'
const materialUrl = 'https://d78uk2n5h6.feishu.cn/drive/folder/Bm7Rfm1T9l7VRxdEjVdcBzPqnDd?from=from_copylink'

function goToStar() {
  starClicked.value = true
  window.open(repoUrl, '_blank')
}
function fakeCheckStar() {
  loading.value = true
  setTimeout(() => {
    isStar.value = true
    loading.value = false
  }, 1200)
}
</script>

<style scoped>
.vp-card.vp-learning-material {
  margin: 24px 0;
  padding: 32px 24px 24px 24px;
  background: var(--vp-c-bg, #fff);
  border-radius: 12px;
  box-shadow: var(--vp-shadow-2, 0 2px 12px rgba(60,60,60,0.07));
  border: 1px solid var(--vp-c-divider, #e6f4ff);
  max-width: 420px;
}
.github-icon {
  display: inline-block;
  vertical-align: middle;
  margin-bottom: 2px;
  color: #24292f;
}
.vp-btn.star-btn {
  display: inline-flex;
  align-items: center;
  gap: 2px;
  padding: 8px 20px;
  font-size: 16px;
  border-radius: 6px;
  border: none;
  background: var(--vp-c-brand, #1677ff);
  color: #fff;
  font-weight: 600;
  cursor: pointer;
  margin-top: 8px;
  transition: background 0.2s, color 0.2s;
}
.vp-btn.star-btn:hover {
  background: var(--vp-c-brand-dark, #0958d9);
  color: var(--vp-c-bg, #e6f4ff);
}
.vp-btn.star-check {
  background: var(--vp-c-success, #52c41a);
  color: #fff;
}
.vp-btn.star-check:hover {
  background: #389e0d;
  color: #fff;
}
.star-link {
  display: inline-block;
  margin-top: 12px;
  font-size: 16px;
  color: var(--vp-c-brand, #1677ff);
  text-decoration: underline;
}
.star-tip-text {
  margin-bottom: 18px;
  font-size: 16px;
  line-height: 1.7;
  color: var(--vp-c-brand, #1677ff);
  background: var(--vp-c-bg-soft, #e6f4ff);
  border-radius: 6px;
  padding: 8px 12px;
  display: inline-block;
  font-weight: 500;
}
.star-success {
  color: var(--vp-c-success, #52c41a);
  font-weight: 600;
  margin-bottom: 12px;
}
.star-highlight {
  color: var(--vp-c-brand, #1677ff);
  font-weight: bold;
}
.star-highlight-link {
  color: var(--vp-c-brand, #1677ff);
  font-weight: bold;
  margin-left: 2px;
  text-decoration: underline;
}
</style>
