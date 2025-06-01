<template>
  <section class="hero-section">
    <v-container>
      <div class="hero-content">
        <v-avatar :size="isMobile ? 120 : 160" class="mb-6">
          <v-img :src="profilePic" alt="Profile Picture" class="profile-image" />
        </v-avatar>

        <h1 class="mb-2 name-heading">
          <span v-if="!isMobile">LOKESWARI MADHUSUDHANA</span>
          <span v-else>LOKESWARI<br>MADHUSUDHANA</span>
        </h1>
        
        <h2 class="mb-6 title-heading">
          <span v-if="!isMobile">FRONT-END DEVELOPER · UI/UX DESIGNER</span>
          <span v-else>FRONT-END DEVELOPER<br>UI/UX DESIGNER</span>
        </h2>

        <div class="button-group mb-6">
          <v-btn 
            color="success" 
            class="action-btn" 
            :class="{ 'mobile-btn': isMobile }"
            @click="scrollTo('contact')"
          >
            Hire me
          </v-btn>
          <v-btn 
            color="success" 
            class="action-btn" 
            :class="{ 'mobile-btn': isMobile }"
            @click="downloadCV"
          >
            Download CV
          </v-btn>
        </div>
      </div>
    </v-container>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted, computed } from 'vue'
import profilePic from '../assets/profile.jpeg'

// Responsive design
const windowWidth = ref(window.innerWidth)
const isMobile = computed(() => windowWidth.value < 768)

const updateWindowWidth = () => {
  windowWidth.value = window.innerWidth
}

const scrollTo = (sectionId: string): void => {
  const el = document.getElementById(sectionId)
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' })
  }
}

const downloadCV = (): void => {
  window.open('/Lokeswari_Cv.pdf', '_blank')
}

onMounted(() => {
  window.addEventListener('resize', updateWindowWidth)
  updateWindowWidth() // Ensure initial width is set
})

onUnmounted(() => {
  window.removeEventListener('resize', updateWindowWidth)
})
</script>

<style scoped>
.hero-section {
  background: url("@/assets/hero-bg.jpg") center/cover no-repeat;
  width: 100%;
  min-height: 85vh;
  padding-top: 80px;
  overflow-x: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  position: relative;
}

.hero-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.4);
  z-index: 1;
}

.hero-content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  max-width: 800px;
  margin: 0 auto;
}

h1, h2 {
  color: white;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
}

.name-heading {
  font-weight: 700;
  letter-spacing: 1px;
  transition: all 0.3s ease;
}

.title-heading {
  font-weight: 500;
  letter-spacing: 0.5px;
  opacity: 0.9;
}

.profile-image {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid white;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
  transition: all 0.3s ease;
}

.button-group {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 16px;
}

.action-btn {
  font-weight: 500;
  letter-spacing: 0.5px;
  padding: 0 24px !important;
  height: 48px !important;
  border-radius: 4px;
  text-transform: none;
  transition: all 0.3s ease;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.action-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
}

/* Mobile styles */
@media (max-width: 767px) {
  .hero-section {
    padding-top: 100px;
    min-height: 90vh;
  }
  
  .name-heading {
    font-size: 1.8rem;
    line-height: 1.3;
  }
  
  .title-heading {
    font-size: 1.2rem;
    line-height: 1.4;
  }
  
  .mobile-btn {
    width: 100%;
    margin-bottom: 8px;
    height: 44px !important;
  }
  
  .button-group {
    flex-direction: column;
    width: 100%;
    max-width: 280px;
  }
}

/* Tablet styles */
@media (min-width: 768px) and (max-width: 1023px) {
  .hero-section {
    min-height: 80vh;
  }
  
  .name-heading {
    font-size: 2.2rem;
  }
  
  .title-heading {
    font-size: 1.4rem;
  }
}
</style>
