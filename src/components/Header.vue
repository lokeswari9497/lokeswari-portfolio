<template>
  <v-app-bar 
    class="app-header" 
    elevation="5" 
    :height="isMobile ? 72 : 96" 
    scroll-behavior="elevate"
    :color="transparent ? 'transparent' : undefined"
    :class="{ 'scrolled': !transparent }"
  >
    <v-container fluid>
      <div class="d-flex align-center header-content">
        <!-- App Title (Mobile + Desktop) -->
        <div class="header-left">
          <router-link to="/" class="text-decoration-none">
            <v-app-bar-title class="text-white d-flex align-center">
              <div>
                <template v-if="!isMobile">
                  <span class="title-text">Lokeswari Madhusudhana</span>
                </template>
                <template v-else>
                  <span class="title-text">Lokeswari</span>
                </template>
              </div>
            </v-app-bar-title>
          </router-link>
        </div>

        <!-- Desktop Navigation -->
        <div v-if="!isMobile" class="desktop-nav">
          <v-btn
            v-for="link in links"
            :key="link.text"
            :to="link.href"
            class="nav-btn"
            variant="plain"
            @click.prevent="scrollToSection(link.href)"
          >
            {{ link.text }}
            <div class="nav-btn-underline"></div>
          </v-btn>
        </div>

        <!-- Mobile Hamburger Menu -->
        <div v-if="isMobile" class="mobile-nav">
          <v-menu 
            location="bottom end" 
            transition="slide-y-transition"
          >
            <template #activator="{ props }">
              <v-btn 
                icon 
                v-bind="props"
                class="menu-btn"
                color="white"
                variant="plain"
              >
                <v-icon size="28">mdi-menu</v-icon>
              </v-btn>
            </template>
            <v-card class="mobile-menu">
              <v-list>
                <v-list-item
                  v-for="link in links"
                  :key="link.text"
                  @click.prevent="scrollToSection(link.href)"
                  class="mobile-menu-item"
                >
                  <v-list-item-title>{{ link.text }}</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-card>
          </v-menu>
        </div>
      </div>
    </v-container>
  </v-app-bar>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted, computed } from 'vue'

const links = [
  { text: 'About', href: '#about' },
  { text: 'Skills', href: '#skills' },
  { text: 'Experience', href: '#experience' },
  { text: 'Contact', href: '#contact' },
]

// Responsive design - explicitly set mobile breakpoint at 768px (md breakpoint)
const windowWidth = ref(window.innerWidth)
const isMobile = computed(() => windowWidth.value < 768)

// Transparent header on top
const scrollPosition = ref(0)
const transparent = computed(() => scrollPosition.value < 50)

const updateScroll = () => {
  scrollPosition.value = window.scrollY
}

const updateWindowWidth = () => {
  windowWidth.value = window.innerWidth
}

const scrollToSection = (selector: string): void => {
  const target = document.querySelector(selector)
  if (target) {
    target.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}

onMounted(() => {
  window.addEventListener('scroll', updateScroll)
  window.addEventListener('resize', updateWindowWidth)
  updateScroll()
  updateWindowWidth() // Ensure initial width is set
})

onUnmounted(() => {
  window.removeEventListener('scroll', updateScroll)
  window.removeEventListener('resize', updateWindowWidth)
})
</script>

<style scoped>
.app-header {
  width: 100%;
  max-width: 100%;
  background-color: #378C3F !important;
  transition: all 0.3s ease;
}

.scrolled {
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.15) !important;
}

.transparent {
  background-color: transparent !important;
  box-shadow: none !important;
}

.header-content {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.header-left {
  display: flex;
  align-items: center;
}

.title-text {
  font-weight: 600;
  letter-spacing: 0.5px;
  transition: all 0.3s ease;
  color: white;
}

.white-text {
  color: white;
}

.desktop-nav {
  display: flex;
  align-items: center;
  margin-left: 20px;
}

.mobile-nav {
  display: flex;
  align-items: center;
  margin-left: auto; /* Push to the right */
}

.nav-btn {
  font-weight: 500;
  font-size: 16px;
  margin: 0 12px;
  color: white !important;
  opacity: 0.9;
  transition: all 0.3s ease;
  position: relative;
  padding-bottom: 4px;
}

.nav-btn:hover {
  opacity: 1;
}

.nav-btn-underline {
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 2px;
  background-color: white;
  transition: all 0.3s ease;
  transform: translateX(-50%);
}

.nav-btn:hover .nav-btn-underline {
  width: 70%;
}

.menu-btn {
  transition: all 0.3s ease;
  color: white !important;
}

.menu-btn:hover {
  background-color: rgba(255, 255, 255, 0.1);
}

.mobile-menu {
  border-radius: 8px;
  overflow: hidden;
}

.mobile-menu-item {
  transition: background-color 0.2s ease;
}

.mobile-menu-item:hover {
  background-color: transparent;
}

/* Ensure mobile styles are applied at the right breakpoint */
@media (max-width: 767px) {
  .nav-btn {
    margin: 0 8px;
    font-size: 14px;
  }
  
  .mobile-nav {
    margin-left: auto;
  }
}
</style>
