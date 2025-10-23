<template>
  <section class="profile-card" role="region" aria-label="Profile">
    <div class="avatar-wrap">
      <img src="/src/assets/avatar.jpg" alt="Wei C 頭像" class="avatar" />
      <!-- 小插畫或簽名 -->
      <img src="/src/assets/illustration.svg" alt="" class="illust" />
    </div>

    <h1 class="name">魏可昕 (Wei C)</h1>
    <p class="title">前端工程師 / UI 整合</p>

    <p class="tagline">喜歡把設計帶入前端。熟 React、Vue，精於互動與 UX 優化。</p>

    <!-- 可選短列表：技術與狀態 -->
    <ul class="meta">
      <li>主要技術：React · Vue · JS</li>
      <li>可到職：2 週內</li>
    </ul>
  </section>
</template>

<script setup>
</script>

<style scoped>
.profile-card{
  background: white;
  border-radius: 14px;
  padding: 18px;
  width: 92%;
  max-width: 420px;
  margin: 8px auto;
  box-shadow: 0 8px 20px rgba(0,0,0,0.08);
  text-align:center;
}
.avatar-wrap{
  position: relative;
  display:inline-block;
}
.avatar{
  width: 92px;
  height: 92px;
  border-radius: 50%;
  object-fit:cover;
  border:4px solid #fff;
  box-shadow: 0 6px 18px rgba(0,0,0,0.08);
}
.illust{
  position: absolute;
  right: -10px;
  top: -10px;
  width: 46px;
  opacity:0.95;
}
.name{ font-size: 1.1rem; margin-top: 10px; font-weight:700; }
.title{ font-size: .9rem; color:#666; margin-top:4px;}
.tagline{ font-size: .85rem; color:#444; margin-top:10px; line-height:1.3; }
.meta{ margin-top:12px; font-size:.78rem; color:#666; list-style:none; padding:0; }
.meta li{ margin: 4px 0;}
</style>
