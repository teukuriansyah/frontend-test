<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import Foto1 from "../assets/Team1.jpg"
import Foto2 from "../assets/Team2.jpg"
import Foto3 from "../assets/Team3.jpg"
import Foto4 from "../assets/Team4.jpg"
import Foto5 from "../assets/Team5.jpg"
import Foto6 from "../assets/Team6.jpg"
import Foto7 from "../assets/Team7.jpg"
import Foto8 from "../assets/Team8.png"
import Foto9 from "../assets/Team9.jpg"
import Foto10 from "../assets/Team10.jpg"
import Foto11 from "../assets/627fc7fcdc0f8e9cbcc8ffed_isa-logo-dog-clean.svg"
import Foto12 from "../assets/627fc81139e6f5dca2d02054_isa-logo-cat-clean.svg"

  const foundationTeam = [
    {
      name: "Daryna Deriy",
      position: "Chairman of the Board",
      image: Foto1
    },
    {
      name: "Polina Snisarenko-Kulchytska",
      position: "Curator of the Foundation",
      image: Foto2
    },
    {
      name: "Bohdan Kulchytsky",
      position: "Executive Manager",
      image: Foto3
    },
    {
      name: "Mykhaylo Deriy",
      position: "Operation Manager",
      image: Foto4
    },
    {
      name: "Ksenia Nikishina",
      position: "Office manager",
      image: Foto5
    },
    {
      name: "Anna Andriychuk",
      position: "SMM-manager",
      image: Foto6
    },
    {
      name: "Anastasia Kovalchuk",
      position: "Director",
      image: Foto7
    },
    {
      name: "Basil Gloo",
      position: "Web Developer",
      image: Foto8
    },
    {
      name: "Lina Yakobchuk",
      position: "Designer",
      image: Foto9
    },
    {
      name: "Anastasia Yevchenko",
      position: "Translator",
      image: Foto10
    },
    {
      name: "Office Manager",
      position: "open vacancy",
      image: Foto11
    },
    {
      name: "SEO specialist",
      position: "open vacancy",
      image: Foto12
    }
  ];  
  
const teamCards = ref([])

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)
  
  // Animasi untuk header
  gsap.from('.team-header h1', {
    scrollTrigger: {
      trigger: '.team-container',
      start: 'top 70%',
      toggleActions: 'play none none none'
    },
    y: 50,
    opacity: 0,
    duration: 0.8,
    ease: 'power2.out'
  })
  
  gsap.from('.team-header p', {
    scrollTrigger: {
      trigger: '.team-container',
      start: 'top 65%',
      toggleActions: 'play none none none'
    },
    y: 30,
    opacity: 0,
    duration: 0.8,
    delay: 0.2,
    ease: 'power2.out'
  })
  
  // Animasi untuk team cards
  gsap.from(teamCards.value, {
    scrollTrigger: {
      trigger: '.team-grid',
      start: 'top 75%',
      toggleActions: 'play none none none'
    },
    y: 80,
    opacity: 0,
    duration: 0.8,
    stagger: {
      amount: 0.6,
      grid: [3, 2], // Sesuai dengan grid layout (3 kolom di desktop, 2 di mobile)
      from: 'center' // Animasi mulai dari tengah
    },
    ease: 'back.out(1.2)'
  })
  
  // Animasi hover tambahan
  teamCards.value.forEach(card => {
    gsap.to(card, {
      y: -4,
      boxShadow: '4px 4px 0 #000',
      duration: 0.3,
      paused: true,
      ease: 'power1.out'
    })
    
    card.addEventListener('mouseenter', () => gsap.to(card, { duration: 0.3, y: -4, boxShadow: '4px 4px 0 #000' }))
    card.addEventListener('mouseleave', () => gsap.to(card, { duration: 0.3, y: 0, boxShadow: 'none' }))
  })
})
</script>

<template>
  <div class="team-container">
    <div class="team-header">
      <h1>Our team</h1>
      <p>consists of completely different people who are united by a common desire - to help</p>
    </div>
    <div class="team-grid">
      <div 
        v-for="(member, index) in foundationTeam" 
        :key="index" 
        class="team-card"
        ref="teamCards"
      >
        <img :src="member.image" :alt="`Portrait of ${member.name}`" class="team-image" />
        <h2 class="team-name">{{ member.name }}</h2>
        <p class="team-position">{{ member.position }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.team-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 2rem;
  overflow: hidden;
}

.team-header {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  margin-bottom: 1rem;
}

.team-header h1 {
  font-weight: bold;
  font-size: 2.25rem;
  line-height: 2.5rem;
  will-change: transform, opacity;
}

.team-header p {
  font-size: 0.875rem;
  line-height: 1.25rem;
  will-change: transform, opacity;
}

.team-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.75rem;
}

.team-card {
  background-color: #fef08a;
  padding: 0.75rem;
  border: 4px solid #000;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  will-change: transform, opacity, box-shadow;
  box-shadow: none;
}

.team-image {
  width: 100%;
  height: auto;
  filter: grayscale(100%);
  transition: filter 0.3s ease;
  will-change: filter;
}

.team-card:hover .team-image {
  filter: grayscale(0%);
}

.team-name {
  font-size: 0.875rem;
  font-weight: 500;
  text-align: center;
}

.team-position {
  font-size: 0.75rem;
  text-align: center;
  color: #4b5563;
}

.team-card:has(img[alt*="vacancy"]) {
  background-color: #fde047;
}

/* Responsive design */
@media (min-width: 768px) {
  .team-container {
    padding: 5rem;
  }
  
  .team-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
  }
  
  .team-header h1 {
    font-size: 2.5rem;
  }
  
  .team-header p {
    font-size: 1rem;
  }
}
</style>