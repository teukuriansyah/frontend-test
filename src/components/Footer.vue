<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import foto from "../assets/62647f9fbe07235ba9b28d67_star-white-with-animals.svg"
import Patreon from "../assets/6274440c6a0ab7631dce0cd1_9055888_patreon_bxl.svg"
import Instagram from "../assets/6274449bf840c377311f2e08_9055851_instagram_bxl.svg"
import Facebook from "../assets/627443d78de17d2c59c8352c_9055795_facebook_bxl.svg"
import Telegram from "../assets/627443f9ac91b492e4c220ba_9055800_telegram_bxl.svg"
import Youtube from "../assets/6274433d06989d76edcff015_9055867_youtube_bxl-1.svg"

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)
  
  gsap.from('.logo', {
    scrollTrigger: {
      trigger: '.logo',
      start: 'top 75%',
      toggleActions: 'play none none none'
    },
    scale: 0.9,
    opacity: 0,
    duration: 1,
    ease: 'power2.out'
  })
})
</script>

<template>
  <div class="contact-container">
    <div class="contact-info">
      <h1>Contact us</h1>
      <p>Kyiv, Ukraine</p>
      <p>mail@isa.co.ua</p>
    </div>
    <div class="social-links">
      <ul>
        <li>
          <a href="#"><img :src="Youtube" alt="YouTube" /></a>
        </li>
        <li>
          <a href="#"><img :src="Instagram" alt="Instagram" /></a>
        </li>
        <li>
          <a href="#"><img :src="Facebook" alt="Facebook" /></a>
        </li>
        <li>
          <a href="#"><img :src="Patreon" alt="Patreon" /></a>
        </li>
        <li>
          <a href="#"><img :src="Telegram" alt="Telegram" /></a>
        </li>
      </ul>
    </div>
    <div class="logo">
      <img :src="foto" alt="ISA Logo" />
    </div>
  </div>
</template>

<style scoped>
.contact-container {
  display: flex;
  flex-direction: column;
  background-color: #22c55e; 
  gap: 1rem;
  padding: 2rem; 
}

.contact-info h1 {
  font-weight: 700;
  font-size: 2.25rem; 
  line-height: 2.5rem; 
  margin-bottom: 0.5rem; 
}

.contact-info p {
  margin-bottom: 0.25rem; 
}

.social-links ul {
  display: flex;
  gap: 0.75rem; 
  list-style: none;
  padding: 0;
  margin: 0;
}

.social-links img {
  width: 32px;
  height: 32px;
  transition: transform 0.2s ease;
}

.social-links img:hover {
  transform: scale(1.1);
}

.logo {
  margin-top:40px
}

.logo img {
  max-width: 100%;
  height: auto;
}

@media (min-width: 768px) {
  .contact-container {
    padding: 5rem; 
  }
  
  .social-links img {
    width: 40px;
    height: 40px;
  }
}
</style>