<template>
  <!-- Banner -->
  <div class="banner"></div>

  <div class="page">

    <!-- 個人資訊卡 -->
    <section class="profile">
      <img :src="avatar" alt="魏可昕 WEI, KO HSIN" class="avatar" />
      <h1 class="name">魏可昕 <span>WEI, KO HSIN</span></h1>
      <p class="title">
        前端工程師 / 網頁設計師<br>
        <span>Frontend Engineer / Web Designer</span>
      </p>

      <!-- 聯絡資訊 -->
      <div class="contact-links" role="region" aria-label="Contact Links">
        <!-- LinkedIn -->
        <a :href="linkedin" target="_blank" rel="noopener noreferrer"
           class="linkedin-link"
           @mouseover="hover.linkedin = true"
           @mouseleave="hover.linkedin = false">
          <img :src="hover.linkedin ? linkedinHoverIcon : linkedinIcon" alt="LinkedIn" class="linkedin-img" />
        </a>

        <!-- 電話與 Email 垂直排列 -->
        <div class="contact-column">
          <a :href="'tel:' + phone" class="contact-item">
            <img :src="phoneIcon" alt="phone" class="icon" />
            <span class="contact-text">{{ phone }}</span>
          </a>

          <a :href="'mailto:' + email" class="contact-item email-item">
            <img :src="mailIcon" alt="email" class="icon" />
            <span class="contact-text">{{ email }}</span>
          </a>
        </div>
      </div>
<!-- 作品集按鈕 --> <section class="files"> <a :href="portfolioView" target="_blank" class="btn btn-portfolio"> 作品集 Portfolio <img :src="downloadIcon" alt="download" class="downloadicon" /> </a> <a :href="resumeView" target="_blank" class="btn btn-resume"> 履歷 Resume <img :src="downloadIcon" alt="download" class="downloadicon" /> </a> </section>
      <!-- 個人介紹 -->
                 <div class="divider"></div>
<p class="intro">
  <span class="intro-title zh">
    跨領域設計 <span class="divider-x">×</span> 前端開發 <span class="divider-x">×</span> 團隊領導
  </span><br>
  擁有 5 年跨領域經驗，專長於前端開發、UI/UX 與平面/動態設計，熟悉設計系統與品牌一致性。<br>
  能快速將設計概念轉為響應式網站（RWD），兼顧美感與使用者體驗。<br>
  <br>
  <span class="intro-title en">
    Cross-disciplinary Design <span class="divider-x">×</span> Frontend Development <span class="divider-x">×</span> Team Leadership
  </span><br>
  5+ years of experience in frontend development, UI/UX, and graphic & motion design.<br>
  Skilled in turning design concepts into responsive websites (RWD) while maintaining aesthetic quality and user focus.<br>
</p>


      <!-- intro 下方分隔線 -->
      <div class="divider"></div>
    </section>

    <!-- 技能區 -->
<section class="skills">
  <h2 class="section-title">技能 <span>SKILLS</span></h2>

  <!-- 無限輪播區 -->
  <div class="icon-marquee">
    <div class="marquee-track">
      <img
        v-for="(icon, index) in [...iconUrls, ...iconUrls]" 
        :key="index"
        :src="icon"
        class="skill-icon"
        alt="Skill icon"
      />
    </div>
  </div>

  <!-- 技能標籤 -->
  <div class="skill-tags">
    <span v-for="tag in skillTags" :key="tag" class="tag">{{ tag }}</span>
  </div>
</section>




    <!-- 前端作品區 -->
    <section class="projects">
      <h2 class="section-title">前端開發作品<br><span>Frontend Projects</span></h2>

      <div class="project-card" v-for="(p, i) in projects" :key="i">
        <a :href="p.link" target="_blank" style="display: contents; color: inherit; text-decoration: none;">
          <img :src="p.image" :alt="p.nameZh" class="project-img" />
          <div class="project-info">
            <h3>{{ p.nameZh }} <span class="project-english">{{ p.nameEn }}</span></h3>
            <p class="date">{{ p.date }}</p>
            <p>{{ p.desc }}</p>
<div class="tools">
  <span
    v-for="tool in p.tools.split(',')"
    :key="tool"
    class="tag"
  >
    {{ tool.trim() }}
  </span>
</div>
          </div>
        </a>
      </div>
    </section>

    <div class="footer-note">© 2025 WEI,KO HSIN</div>
  </div>
</template>


<script setup>
import { ref } from 'vue'

// Banner 與 avatar
const avatar = new URL('/src/assets/avatar.jpeg', import.meta.url).href

// 技能 icons
const icons = ['github','axure','figma','sketch','pr','ae','ai','ps','id','github','axure','figma','sketch','pr','ae','ai','ps','id']
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
    nameZh: '北花冊 (團體協作)',
    nameEn: 'Bloomchure',
    desc: '北區賞花季，一頁收藏所有花事，北區花卉資訊整合平台',
    date: '2025',
    tools: 'React, SASS, JavaScript, RWD, Swiper, Api, Figma',
    image: new URL('/src/assets/project1.svg', import.meta.url).href,
    link: 'https://ovopenguin.github.io/myBloomProject/'
  },
  {
    nameZh: '個人作品網站',
    nameEn: 'My Portfolio Website',
    desc: '前端開發、UI/UX、平面設計、動畫設計作品',
    date: '2025',
    tools: 'React, CSS, Lottie, Swiper, react-pageflip, Firebase',
    image: new URL('/src/assets/me.svg', import.meta.url).href,
    link: 'https://www.behance.net/gallery/234853575/_'
  },
]
import { onMounted } from 'vue'

onMounted(() => {
  const animatedSections = document.querySelectorAll('.banner, section, .footer-note')

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      const el = entry.target
      if (entry.isIntersecting) {
        // 加上 visible class 播放動畫
        el.classList.add('visible')

        // 移除後重新加上 → 讓動畫可重播
        el.classList.remove('replay')
        void el.offsetWidth // 強制重繪
        el.classList.add('replay')
      } else {
        // 離開畫面時移除 visible，讓下次可重新播放
        el.classList.remove('visible')
      }
    })
  }, { threshold: 0.2 })

  animatedSections.forEach(sec => observer.observe(sec))
})

const hover = ref({ linkedin: false })

// icons
const phoneIcon = new URL('/src/assets/phoneicon.svg', import.meta.url).href
const mailIcon = new URL('/src/assets/mailicon.svg', import.meta.url).href
const linkedinIcon = new URL('/src/assets/Linkedin_b.svg', import.meta.url).href
const linkedinHoverIcon = new URL('/src/assets/Linkedin_hover.svg', import.meta.url).href

const phone = '+88618082691'
const email = 'anna0826777@gmail.com'
const linkedin = 'https://www.linkedin.com/in/ko-hsin-wei-312574241/'

// Google Drive 連結
const resumeDL = 'https://drive.google.com/file/d/1f9maGd0yClzpO4baTS_IM_PUEdiNQSLA/view?usp=sharing'
const portfolioView = 'https://drive.google.com/file/d/1bLJzYLpbAZDSlfzJM4JU8MLznNfZz6Nb/view?usp=sharing'
const resumeView = 'https://drive.google.com/file/d/1f9maGd0yClzpO4baTS_IM_PUEdiNQSLA/view?usp=sharing'
const downloadIcon = new URL('/src/assets/download.svg', import.meta.url).href
</script>
