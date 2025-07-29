<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

import adviRES from '../assets/adviRES.jpg'
import ovidWindLogo from '../assets/ovid-wind-logo.png'
import tbsLogo from '../assets/tbs_logo1-02.png'
import logoLaudis from '../assets/logo_laudis.png'
import downloadLogo from '../assets/download.png'
import photo from '../assets/photo_2022-04-21.jpeg'

const pics = [adviRES, ovidWindLogo, tbsLogo, downloadLogo, logoLaudis, photo]
const partnerItems = ref([])

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)
  
  // Animasi untuk header
  gsap.from('.partners-header h1', {
    scrollTrigger: {
      trigger: '.partners-container',
      start: 'top 70%'
    },
    y: 50,
    opacity: 0,
    duration: 0.8,
    ease: 'power2.out'
  })
  
  gsap.from('.partners-header p', {
    scrollTrigger: {
      trigger: '.partners-container',
      start: 'top 65%'
    },
    y: 30,
    opacity: 0,
    duration: 0.8,
    delay: 0.2,
    ease: 'power2.out'
  })
  
  // Animasi untuk grid items
  gsap.from(partnerItems.value, {
    scrollTrigger: {
      trigger: '.partners-grid',
      start: 'top 75%',
      toggleActions: 'play none none none'
    },
    y: 80,
    opacity: 0,
    duration: 0.8,
    stagger: 0.15,
    ease: 'back.out(1.2)'
  })
})
</script>

<template>
  <div class="partners-container">
    <div class="partners-header">
      <h1>Our partners</h1>
      <p>are take care of our fund and help us with many questions</p>
    </div>
    <div class="partners-grid">
      <div 
        v-for="(pic, index) in pics" 
        :key="index" 
        class="partner-item"
        ref="partnerItems"
      >
        <img :src="pic" :alt="'Partner logo ' + (index + 1)" class="partner-logo"/>
      </div>
    </div>
  </div>
</template>

<style scoped>
.partners-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 2rem;
  overflow: hidden; 
}

.partners-header h1 {
  font-weight: bold;
  font-size: 2.25rem;
  line-height: 2.5rem;
  margin-bottom: 0.5rem;
  will-change: transform, opacity;
}

.partners-header p {
  font-size: 0.875rem;
  line-height: 1.25rem;
  will-change: transform, opacity;
}

.partners-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2.25rem;
}

.partner-item {
  will-change: transform, opacity;
}

.partner-logo {
  width: 100%;
  height: auto;
  filter: grayscale(100%);
  transition: filter 0.3s ease, transform 0.3s ease;
}

.partner-logo:hover {
  filter: grayscale(0%);
  transform: scale(1.05);
}

@media (min-width: 768px) {
  .partners-container {
    padding: 5rem;
  }
  
  .partners-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>