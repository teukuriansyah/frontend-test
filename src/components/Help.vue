<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
  const shelters = [
    "Shelter of Victoria Bulbyna",
    "Shelter of Natalia Tymoshenko",
    "Shelter of Jeanne Sass",
    "Shelter of Victoria Bondarenko",
    "Zoo chance",
    "Save lives",
    "City Center for the Treatment of Animals",
    "Society for the Protection of Animals in Sumy",
    "The right to life",
    "4 paws",
    "The kingdom of cats",
    "Zvir",
    "Mercy",
    "Happy dog",
    "Give me a paw, friend",
    "Friend",
    "Hope",
    "We are for the right to life",
    "Planeta",
    "Second Life",
    "Happy shore",
    "Retrieverteam",
    "Shelter of Irina Dobrolyubova",
    "Matilda",
    "Life",
    "Second chance",
    "SOS",
    "Best friends"
  ];
  
onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)
  
  gsap.from('.shelters-grid', {
    scrollTrigger: {
      trigger: '.shelters-grid',
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
  <div class="shelters-container">
    <div class="shelters-header">
      <h1>We want to help</h1>
      <p>homeless packs, volunteers, guardians, overstayers, shelters and other organisations</p>
    </div>
    
    <div class="shelters-grid">
      <div v-for="(shelter, index) in shelters" :key="index" class="shelter-card">
        <p>{{ shelter }}</p>
      </div>
    </div>
    
    <div class="apply-button-container">
      <button class="apply-button">Apply for help →</button>
    </div>
  </div>
</template>

<style scoped>
.shelters-container {
  background-color: #fbbf24;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 2rem;
}

.shelters-header {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  margin-bottom: 1rem;
}

.shelters-header h1 {
  font-weight: bold;
  font-size: 2.25rem;
  line-height: 2.5rem;
}

.shelters-header p {
  font-size: 0.875rem;
  line-height: 1.25rem;
}

.shelters-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.25rem;
}

.shelter-card {
  border: 2px solid black;
  background-color: white;
  padding: 1.75rem;
  display: flex;
  align-items: center;
  justify-content: center;
  aspect-ratio: 1/1;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.shelter-card:hover {
  transform: scale(1.05);
  box-shadow: 4px 4px 0 black;
}

.shelter-card p {
  font-size: 0.75rem;
  text-align: center;
  line-height: 1.25;
}

.apply-button-container {
  display: flex;
  margin-top: 1.5rem;
}

.apply-button {
  border: 4px solid black;
  font-weight: bold;
  padding: 1rem;
  background-color: #f472b6; 
  cursor: pointer;
  transition: all 0.3s ease;
}

.apply-button:hover {
  background-color: #ec4899;
  transform: translateY(-2px);
  box-shadow: 4px 4px 0 black;
}

@media (min-width: 768px) {
  .shelters-container {
    padding: 5rem;
    gap: 1.5rem;
  }
  
  .shelters-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }
  
  .shelter-card p {
    font-size: 0.875rem;
  }
  
  .apply-button {
    padding: 1.25rem 2rem;
    font-size: 1.125rem;
  }
}
</style>