<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import Foto1 from "../assets/Citizens1.jpg"
import Foto2 from "../assets/Citizens2.jpg"
import Foto3 from "../assets/Citizens3.jpg"
import Foto4 from "../assets/Citizens4.jpg"
import Foto5 from "../assets/Citizens5.jpg"
import Foto6 from "../assets/Citizens6.jpg"
import Foto7 from "../assets/Citizens7.jpg"
import Foto8 from "../assets/Citizens8.jpg"
import Foto9 from "../assets/Citizens9.jpg"
import Foto10 from "../assets/Citizens10.jpg"
import Foto11 from "../assets/Citizens11.jpg"
import Foto12 from "../assets/Citizens12.jpg"
import Foto13 from "../assets/Citizens13.jpg"
import Foto14 from "../assets/Citizens14.jpg"

const supporters = [
    {
      name: "Oleksiy Tritenko",
      profession: "theater and film actor",
      image: Foto1
    },
    {
      name: "Stanislav Boklan",
      profession: "People’s Artist of Ukraine",
      image: Foto2
    },
    {
      name: "Alexander Rudinsky",
      profession: "theater and film actor",
      image: Foto3
    },
    {
      name: "Oksana Zhdanova",
      profession: "theater and film actress",
      image: Foto4
    },
    {
      name: "Natalka Denisenko",
      profession: "theater and film actress",
      image: Foto5
    },
    {
      name: "Maksym Samchyk",
      profession: "theater and film actor",
      image: Foto6
    },
    {
      name: "Kateryna Vyshneva",
      profession: "theater and film actress",
      image: Foto7
    },
    {
      name: "Irma Vitovska",
      profession: "Honored Actress of Ukraine",
      image: Foto8
    },
    {
      name: "Igor Portyanko",
      profession: "actor of theater and cinema",
      image: Foto9
    },
    {
      name: "Dmytro Surzhikov",
      profession: "Honored Artist of Ukraine",
      image: Foto10
    },
    {
      name: "Daria Barihashvili",
      profession: "theater and film actress",
      image: Foto11
    },
    {
      name: "Vera Kobzar",
      profession: "theater and film actress",
      image: Foto12
    },
    {
      name: "Andriy Fedynchyk",
      profession: "theater and film actor",
      image: Foto13
    },
    {
      name: "Anastasia Nesterenko",
      profession: "theater and film actress",
      image: Foto14
    }
  ]
  
onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)
  
  gsap.from('.supporter-card', {
    scrollTrigger: {
      trigger: '.supporter-card',
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
  <div class="supporters-container">
    <div class="supporters-header">
      <h1>Socially active citizens</h1>
      <p>support us</p>
    </div>
    <div class="supporters-grid">
      <div v-for="(data, index) in supporters" :key="index" class="supporter-card">
        <img :src="data.image" :alt="`Portrait of ${data.name}`" class="supporter-image"/>
        <h2 class="supporter-name">{{ data.name }}</h2>
        <p class="supporter-profession">{{ data.profession }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.supporters-container {
  display: flex;
  flex-direction: column;
  background-color: #f9a8d4;
  gap: 1rem; 
  padding: 2rem; 
}

.supporters-header {
  display: flex;
  flex-direction: column;
  gap: 0.75rem; 
}

.supporters-header h1 {
  font-weight: bold;
  font-size: 1.5rem; 
  line-height: 2rem; 
}

.supporters-header p {
  font-size: 0.875rem; 
  line-height: 1.25rem;
}

.supporters-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.75rem; 
}

.supporter-card {
  padding: 0.75rem; 
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem; 
  border-radius: 0.5rem; 
  transition: transform 0.3s ease, background-color 0.3s ease;
}

.supporter-image {
  width: 100%;
  height: auto;
  filter: grayscale(100%);
  transition: filter 0.3s ease;
}

.supporter-name {
  font-size: 0.875rem; 
  line-height: 1.25rem; 
  text-align: center;
  font-weight: 500;
}

.supporter-profession {
  font-size: 0.75rem; 
  line-height: 1rem; 
  text-align: center;
  color: #4b5563; 
}

@media (min-width: 768px) {
  .supporters-container {
    padding: 5rem; 
  }
  
  .supporters-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 1.25rem; 
  }
  
  .supporter-card {
    padding: 1rem; 
  }
}
</style>