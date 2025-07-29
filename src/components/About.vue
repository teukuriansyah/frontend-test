<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)
  
  gsap.from('.video-container', {
    scrollTrigger: {
      trigger: '.video-container',
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
  <div class="about-container">
    <section class="about-section">
      <h1 class="about-title">We are</h1>
      <p class="about-text">team of like-minded people, socially active companies, media personalities, volunteers who help low-income shelters and foster carers to support homeless animals.</p>
    </section>

    <section class="about-section">
      <h1 class="about-title">Our primary goal</h1>
      <p class="about-text">is to provide animals with the most necessary things - food, medicine, and urgent needs for the livelihood of shelters. We believe in our power and the power of conscious citizens who care about the environment and their health, who understand the importance of helping each other, especially our little friends. Growth begins with your care for your loved ones. Animals are one of the closest creatures to humans who remain with us throughout our lives. We all know the healing power of warmth, grace, and big loving eyes.</p>
      
      <div class="quote-container">
        <div class="quote-box">
          <p class="quote-text"><i>"Animals need to have friends. Just like humans."</i></p>
          <p class="quote-author"><i>- James Herriot, All Creatures Great and Small</i></p>
        </div>
      </div>

      <p class="about-text closing-text">Who else if not we should support our younger brothers, especially in difficult times? Let's be friends!</p>
    </section>

    <div class="video-container">
      <iframe 
        src="https://www.youtube.com/embed/5Wk1rp99B7o" 
        title="About our organization" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen
        class="youtube-embed"
      ></iframe>
    </div>
  </div>
</template>

<style scoped>
.about-section {
  will-change: transform, opacity;
}

.quote-box {
  will-change: transform, opacity;
}

.video-container {
  will-change: transform, opacity;
  transform-origin: center bottom;
}

.about-container {
  padding: 1.25rem;
  display: flex;
  flex-direction: column;
  gap: 1.75rem;
  overflow-x: hidden; 
}

.about-container {
  padding: 1.25rem;
  display: flex;
  flex-direction: column;
  gap: 1.75rem;
}

.about-section {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.about-title {
  font-size: 1.875rem;
  font-weight: bold;
  line-height: 2.25rem;
}

.about-text {
  font-size: 0.875rem;
  line-height: 1.25rem;
}

.quote-container {
  padding-left: 1rem;
}

.quote-box {
  border-left: 4px solid #f9a8d4;
  padding: 1.25rem;
  border-radius: 0 0.5rem 0.5rem 0;
}

.quote-text {
  font-size: 0.875rem;
  font-style: italic;
  line-height: 1.25rem;
  margin-bottom: 0.5rem;
}

.quote-author {
  font-size: 0.875rem;
  font-style: italic;
  line-height: 1.25rem;
  color: #6b7280; 
}

.closing-text {
  margin-top: 0.75rem;
}

.video-container {
  position: relative;
  overflow: hidden;
  width: 100%;
  padding-top: 56.25%;
  margin-top: 1rem;
}

.youtube-embed {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  width: 100%;
  height: 100%;
  border-radius: 0.5rem;
}

@media (min-width: 768px) {
  .about-container {
    padding: 2.5rem;
    gap: 2.5rem;
  }
  
  .about-title {
    font-size: 2.25rem;
    line-height: 2.5rem;
  }
  
  .about-text, .quote-text, .quote-author {
    font-size: 1rem;
    line-height: 1.5rem;
  }
  
  .quote-box {
    padding: 1.5rem;
  }
  
  .video-container {
    margin-top: 1.5rem;
  }
}
</style>