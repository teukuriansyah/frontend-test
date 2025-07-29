<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)
  
  gsap.from('.project-card', {
    scrollTrigger: {
      trigger: '.project-card',
      start: 'left 75%',
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
  <div class="projects-container">
    <div class="projects-header">
      <h1>Our projects</h1>
      <p>are very different in terms of priority, scale and complexity of implementation</p>
    </div>
    
    <div class="project-card emergency-aid">
      <h2>Emergency Aid. WAR 2022.</h2>
      <p>providing food and medicine to the shelters and animals which lost their homes and families due to the war</p>
    </div>
    
    <div class="project-card feed-line">
      <h2>Non-commercial feed line</h2>
      <p>construction of industrial production base where food for shelters will be produced on a free basis</p>
    </div>
    
    <div class="project-card education">
      <h2>Education and Control</h2>
      <p>lectures on communication, organisation and coordination of processes, control over the use of aid</p>
    </div>
  </div>
</template>

<style scoped>
.projects-container {
  background-color: #3b82f6;
  display: flex;
  flex-direction: column;
  gap: 1rem; 
  padding: 2rem; 
  color: white;
}

.projects-header {
  display: flex;
  flex-direction: column;
  gap: 0.75rem; 
  margin-bottom: 1rem;
}

.projects-header h1 {
  font-weight: bold;
  font-size: 2.25rem; 
  line-height: 2.5rem; 
}

.projects-header p {
  font-size: 0.875rem; 
  line-height: 1.25rem; 
}

.project-card {
  border: 2px solid white;
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.project-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
}

.project-card h2 {
  font-weight: bold;
  font-size: 1.5rem;
  line-height: 2rem;
}

.project-card p {
  font-size: 0.875rem; 
  line-height: 1.25rem; 
}

.emergency-aid {
  background-color: black;
}

.feed-line {
  background-color: #22c55e; 
}

.education {
  background-color: #f9a8d4; 
}

@media (min-width: 768px) {
  .projects-container {
    padding: 5rem; 
  }
  
  .projects-header h1 {
    font-size: 2.5rem;
  }
  
  .projects-header p {
    font-size: 1rem; 
  }
  
  .project-card {
    padding: 2rem;
  }
  
  .project-card h2 {
    font-size: 1.75rem; 
  }
  
  .project-card p {
    font-size: 1rem;
  }
}
</style>