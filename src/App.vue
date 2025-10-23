<template>
  <!-- Banner -->
  <div class="banner"></div>

  <div class="page">

    <!-- 個人資訊卡 -->
    <section class="profile">
      <img :src="avatar" alt="魏可昕 WEI, KO HSIN" class="avatar" />

      <h1 class="name">魏可昕 <span>WEI, KO HSIN</span></h1><!-- 聯絡資訊 -->
<section class="contact-links" role="region" aria-label="Contact Links">
  <!-- LinkedIn -->
  <a :href="linkedin" target="_blank" rel="noopener noreferrer" class="linkedin-link">
    <img :src="linkedinIcon" alt="LinkedIn" class="linkedin-img" />
  </a>

  <!-- 電話與 Email 水平排列 -->
  <div class="contact-row">
    <!-- 電話 -->
    <a :href="'tel:' + phone" class="contact-item" aria-label="Call phone">
      <span class="icon">📞</span>
      <span class="contact-text">{{ phone }}</span>
    </a>

    <!-- Email -->
    <a :href="'mailto:' + email" class="contact-item" aria-label="Send email">
      <span class="icon">✉️</span>
      <span class="contact-text">{{ email }}</span>
    </a>
  </div>
</section>
      <p class="title">前端工程師 / 網頁設計師<br><span>Frontend Engineer / Web Designer</span></p>

<p class="intro">
跨領域設計 × 前端開發 × 團隊領導<br>
擁有 5 年跨領域經驗，專長於前端開發、UI/UX 與平面/動態設計，熟悉設計系統與品牌一致性。<br>
能快速將設計概念轉為響應式網站（RWD），兼顧美感與使用者體驗。<br>
<br>

Cross-disciplinary Design × Frontend Development × Team Leadership<br>
5+ years of experience in frontend development, UI/UX, and graphic & motion design.<br>
Skilled in turning design concepts into responsive websites (RWD) while maintaining aesthetic quality and user focus.<br>
</p>

    </section>



    <!-- 技能區 -->
    <section class="skills">
      <h2>技能 SKILLS</h2>
      <div class="icon-grid">
        <img v-for="icon in iconUrls" :key="icon" :src="icon" class="skill-icon" />
      </div>
      <div class="skill-tags">
        <span v-for="tag in skillTags" :key="tag" class="tag">{{ tag }}</span>
      </div>
    </section>

    <!-- 作品集按鈕 -->
    <section class="files">
      <a :href="portfolioView" target="_blank" class="btn btn-portfolio">作品集 Portfolio 
        <img :src="downloadIcon" alt="download" class="downloadicon" />
      </a>
      <a :href="resumeView" target="_blank" class="btn btn-resume">履歷 Resume 
        <img :src="downloadIcon" alt="download" class="downloadicon" />
      </a>
    </section>

    <!-- 前端作品區 -->
    <section class="projects">
      <h2>前端開發作品<br><span>Frontend Projects</span></h2>

      <div class="project-card" v-for="(p, i) in projects" :key="i">
  <a :href="p.link" target="_blank" style="display: contents; color: inherit; text-decoration: none;">
    <img :src="p.image" :alt="p.nameZh" class="project-img" />
    <div class="project-info">
      <h3>
        {{ p.nameZh }} 
        <span class="project-english">{{ p.nameEn }}</span>
      </h3>
      <p class="date">{{ p.date }}</p>
      <p>{{ p.desc }}</p>
      <p class="tools">使用技術 / Skills: {{ p.tools }}</p>
    </div>
  </a>
</div>

    </section>

    <div class="footer-note">© 2025 WEI,KO HSIN</div>
  </div>
</template>

<script setup>

// Banner 與 avatar
const avatar = new URL('/src/assets/avatar.jpeg', import.meta.url).href

// 技能 icons
const icons = ['github', 'axure', 'figma', 'sketch', 'pr', 'ae', 'ai', 'ps', 'id']
const iconUrls = icons.map(icon => new URL(`/src/assets/${icon}.svg`, import.meta.url).href)

// 技能 tags
const skillTags = [
  'React', 'Vue', 'HTML', 'CSS', 'SASS',
  'JavaScript', 'RWD', 'Bootstrap', 'Tailwind CSS',
  'Prototype', 'Wireframe'
]

// 作品資料
const projects = [
  {
    nameZh: '北花冊',
    nameEn: 'Bloomchure',
    desc: '北區賞花季，一頁收藏所有花事，北區花卉資訊整合平台',
    date: '2025',
    tools: 'React, SASS, JavaScript, RWD, Swiper, Api, Figma',
    image: new URL('/src/assets/project1.svg', import.meta.url).href,
    link: 'https://ovopenguin.github.io/myBloomProject/' // 點開新分頁
  },
  {
    nameZh: '個人作品網站',
    nameEn: 'My Portfolio Website',
    desc: '前端開發、UI/UX、平面設計、動畫設計作品',
    date: '2025',
    tools: 'React, CSS, Lottie, Swiper, react-pageflip, Firebase',
    image: new URL('/src/assets/me.svg', import.meta.url).href,
    link: 'https://www.behance.net/gallery/234853575/_' // 點開新分頁
  },
]
// LinkedIn icon
const linkedinIcon = new URL('/src/assets/Linkedin_b.svg', import.meta.url).href
const linkedinHoverIcon = new URL('/src/assets/Linkedin_hover.svg', import.meta.url).href

const phone = '+88618082691'
const email = 'anna0826777@gmail.com'
const linkedin = 'https://www.linkedin.com/in/ko-hsin-wei-312574241/'

// 你提供的 Google Drive 連結
const resumeDL = 'https://drive.google.com/file/d/1f9maGd0yClzpO4baTS_IM_PUEdiNQSLA/view?usp=sharing'
const portfolioView = 'https://drive.google.com/file/d/1bLJzYLpbAZDSlfzJM4JU8MLznNfZz6Nb/view?usp=sharing'
const resumeView = 'https://drive.google.com/file/d/1f9maGd0yClzpO4baTS_IM_PUEdiNQSLA/view?usp=sharing'
const downloadIcon = new URL('/src/assets/download.svg', import.meta.url).href
</script>