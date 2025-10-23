<script setup>
</script>

<template>
  <div class="page">
    <!-- 插畫背景（可換成 svg） -->
    <div class="hero-illustration" aria-hidden="true"></div>

    <main class="card-wrap">
      <ProfileCard />
      <ContactLinks />
    </main>

    <footer class="footer-note">Wei C — Digital Business Card</footer>
  </div>
</template>

<script>
import ProfileCard from './components/ProfileCard.vue'
import ContactLinks from './components/ContactLinks.vue'

export default {
  components: { ProfileCard, ContactLinks },
}
</script>
