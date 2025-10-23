<template>
  <section class="links" role="region" aria-label="Contact Links">
    <div class="button-row">
      <!-- 電話：tel: -->
      <a class="btn" :href="'tel:' + phone" aria-label="Call phone">
        📞 電話
      </a>

      <!-- Email：點擊複製（此範例開 email client） -->
      <a class="btn" :href="'mailto:' + email" aria-label="Send email">
        ✉️ Email
      </a>

      <!-- LinkedIn -->
      <a class="btn" :href="linkedin" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn">
        🔗 LinkedIn
      </a>
    </div>

    <div class="file-row">
      <!-- 履歷（預覽新視窗） -->
      <div class="file-card">
        <a :href="resumeView" target="_blank" rel="noopener noreferrer" class="file-link">
          📄 履歷（預覽）
        </a>
        <a :href="resumeDL" target="_blank" rel="noopener noreferrer" class="download" aria-label="Download resume">
          ⤓
        </a>
      </div>

      <!-- 作品集 -->
      <div class="file-card">
        <a :href="portfolioView" target="_blank" rel="noopener noreferrer" class="file-link">
          🧩 作品集（預覽）
        </a>
        <a :href="portfolioDL" target="_blank" rel="noopener noreferrer" class="download" aria-label="Download portfolio">
          ⤓
        </a>
      </div>
    </div>

    <p class="note">點按連結將在新視窗開啟 PDF 預覽；右上下載圖示會導引至雲端下載頁面。</p>
  </section>
</template>

<script setup>
const phone = '0912345678'            // <-- 替換成你的電話（國碼請視情況加入）
const email = 'youremail@example.com' // <-- 替換成你的 email
const linkedin = 'https://www.linkedin.com/in/xxx' // <-- 替換

// 你提供的 Google Drive 連結
const resumeView = 'https://drive.google.com/file/d/1f9maGd0yClzpO4baTS_IM_PUEdiNQSLA/view?usp=sharing'
const resumeDL = 'https://drive.google.com/file/d/1f9maGd0yClzpO4baTS_IM_PUEdiNQSLA/view?usp=sharing'

const portfolioView = 'https://drive.google.com/file/d/1bLJzYLpbAZDSlfzJM4JU8MLznNfZz6Nb/view?usp=sharing'
const portfolioDL = 'https://drive.google.com/file/d/1bLJzYLpbAZDSlfzJM4JU8MLznNfZz6Nb/view?usp=sharing'
</script>

<style scoped>
.links{ width:92%; max-width:420px; margin: 12px auto 60px; text-align:center; }
.button-row{ display:flex; gap:8px; justify-content:center; }
.btn{
  flex:1;
  padding:10px 8px;
  border-radius:10px;
  background: linear-gradient(135deg,#ffe4f0,#f0f8ff);
  text-decoration:none;
  color:#222;
  font-weight:600;
  box-shadow: 0 6px 18px rgba(100,80,160,0.06);
}
.file-row{ display:flex; gap:8px; margin-top:12px; justify-content:center; }
.file-card{
  position:relative;
  background:#fff;
  padding:8px 10px;
  border-radius:10px;
  min-width:140px;
  box-shadow: 0 6px 14px rgba(0,0,0,0.06);
  display:flex;
  justify-content:space-between;
  align-items:center;
}
.file-link{ text-decoration:none; color:#333; font-weight:600; }
.download{ text-decoration:none; font-size:1rem; margin-left:8px; color:#666; }
.note{ margin-top:10px; font-size:.78rem; color:#777; }
</style>
