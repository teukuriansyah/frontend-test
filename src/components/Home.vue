<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import Patreon from "../assets/6274440c6a0ab7631dce0cd1_9055888_patreon_bxl.svg"
import Instagram from "../assets/6274449bf840c377311f2e08_9055851_instagram_bxl.svg"
import Facebook from "../assets/627443d78de17d2c59c8352c_9055795_facebook_bxl.svg"
import Telegram from "../assets/627443f9ac91b492e4c220ba_9055800_telegram_bxl.svg"
import Youtube from "../assets/6274433d06989d76edcff015_9055867_youtube_bxl-1.svg"
import Cat from "../assets/627fc81139e6f5dca2d02054_isa-logo-cat-clean.svg"
import Dog from "../assets/627fc7fcdc0f8e9cbcc8ffed_isa-logo-dog-clean.svg"

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)
  
  gsap.from('.logo-section', {
    scrollTrigger: {
      trigger: '.logo-section',
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
  <div class="hero-container">
    <div class="logo-section">
      <div class="logo-wrapper">
        <img :src="Cat" alt="ISA Cat Logo" class="cat-logo" />
        <div class="logo-text">
          <ul class="brand-name">
            <li>Innovative</li>
            <li>Solutions</li>
            <li>for</li>
            <li>Animals</li>
          </ul>
        </div>
      </div>
      <div class="tagline">
        <span>charity organization</span>
      </div>
    </div>
    
    <div class="social-links">
      <ul>
        <li>
          <a href="#" aria-label="YouTube">
            <img :src="Youtube" alt="YouTube" class="social-icon" />
          </a>
        </li>
        <li>
          <a href="#" aria-label="Instagram">
            <img :src="Instagram" alt="Instagram" class="social-icon" />
          </a>
        </li>
        <li>
          <a href="#" aria-label="Facebook">
            <img :src="Facebook" alt="Facebook" class="social-icon" />
          </a>
        </li>
        <li>
          <a href="#" aria-label="Patreon">
            <img :src="Patreon" alt="Patreon" class="social-icon" />
          </a>
        </li>
        <li>
          <a href="#" aria-label="Telegram">
            <img :src="Telegram" alt="Telegram" class="social-icon" />
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.hero-container {
  height: 100vh;
  background-color: #fbbf24;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1.25rem; 
  padding: 2rem;
}

.logo-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.75rem; 
}

.logo-wrapper {
  display: flex;
  align-items: center;
  gap: 0.75rem; 
}

.cat-logo {
  width: 5rem; 
  height: auto;
}

.brand-name {
  list-style: none;
  padding: 0;
  margin: 0;
}

.brand-name li {
  font-weight: bold;
  font-size: 1.5rem; 
  line-height: 2rem; 
  color: #1f2937; 
}

.tagline span {
  font-size: 0.875rem;
  color: #4b5563; 
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.social-links ul {
  display: flex;
  gap: 0.75rem; 
  list-style: none;
  padding: 0;
  margin: 0;
}

.social-icon {
  width: 2rem; 
  height: 2rem; 
  transition: transform 0.3s ease;
}

.social-icon:hover {
  transform: scale(1.1);
}

@media (min-width: 768px) {
  .hero-container {
    gap: 2rem; 
  }
  
  .cat-logo {
    width: 6rem;
  }
  
  .brand-name li {
    font-size: 2rem; 
    line-height: 2.5rem; 
  }
  
  .tagline span {
    font-size: 1rem; 
  }
  
  .social-icon {
    width: 2.5rem; 
    height: 2.5rem; 
  }
}
</style>