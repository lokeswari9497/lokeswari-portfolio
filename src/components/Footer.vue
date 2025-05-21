<template>
  <v-footer class="footer-section" :class="{ 'py-6': !isMobile, 'py-4': isMobile }">
    <v-container>
      <v-row align="center" justify="space-between" no-gutters>
        <!-- Name or Logo -->
        <v-col cols="12" md="4" class="text-center text-md-start mb-4 mb-md-0">
          <div class="footer-logo">
            <strong class="footer-name">Lokeswari Madhusudhana</strong>
          </div>
        </v-col>

        <!-- Social Links -->
        <v-col cols="12" md="4" class="text-center mb-4 mb-md-0">
          <div class="social-links">
            <v-btn
              icon
              href="https://www.linkedin.com/in/lokeswari-m/"
              target="_blank"
              class="social-btn mx-2"
              variant="plain"
              color="black"
            >
              <v-icon size="24">mdi-linkedin</v-icon>
            </v-btn>
            <v-btn
              icon
              href="https://github.com/lokeswari9497"
              target="_blank"
              class="social-btn mx-2"
              variant="plain"
              color="black"
            >
              <v-icon size="24">mdi-github</v-icon>
            </v-btn>
            <v-btn
              icon
              href="mailto:your-email@example.com"
              class="social-btn mx-2"
              variant="plain"
              color="black"
            >
              <v-icon size="24">mdi-email</v-icon>
            </v-btn>
          </div>
        </v-col>

        <!-- Copyright -->
        <v-col cols="12" md="4" class="text-center text-md-end">
          <small class="copyright-text">&copy; {{ currentYear }} All rights reserved.</small>
        </v-col>
      </v-row>
      
      <!-- Quick Links - Mobile Only -->
      <v-row v-if="isMobile" class="mt-4 pt-4 quick-links-mobile" align="center" justify="center">
        <v-col cols="12" class="text-center">
          <v-btn
            v-for="link in quickLinks" 
            :key="link.text"
            variant="text"
            density="compact"
            class="mx-1 quick-link-btn"
            @click="scrollToSection(link.href)"
          >
            {{ link.text }}
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted, computed } from 'vue'

// Responsive design
const windowWidth = ref(window.innerWidth)
const isMobile = computed(() => windowWidth.value < 768)
const currentYear = new Date().getFullYear()

const quickLinks = [
  { text: 'About', href: '#about' },
  { text: 'Skills', href: '#skills' },
  { text: 'Experience', href: '#experience' },
  { text: 'Contact', href: '#contact' },
]

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
  window.addEventListener('resize', updateWindowWidth)
  updateWindowWidth() // Ensure initial width is set
})

onUnmounted(() => {
  window.removeEventListener('resize', updateWindowWidth)
})
</script>

<style scoped>
.footer-section {
  background: #BDBDBD;
  color: #000000;
  width: 100%;
  transition: all 0.3s ease;
}

.footer-logo {
  display: flex;
  align-items: center;
  justify-content: center;
}

@media (min-width: 768px) {
  .footer-logo {
    justify-content: flex-start;
  }
}

.footer-name {
  font-size: 1.1rem;
  font-weight: 600;
  transition: all 0.3s ease;
}

.green-text {
  color: #378C3F;
}

.social-links {
  display: flex;
  justify-content: center;
  align-items: center;
}

.social-btn {
  transition: all 0.3s ease;
  opacity: 0.8;
}

.social-btn:hover {
  opacity: 1;
  transform: translateY(-2px);
}

.copyright-text {
  font-size: 0.9rem;
  opacity: 0.8;
}

.quick-links-mobile {
  border-top: 1px solid rgba(0, 0, 0, 0.1);
}

.quick-link-btn {
  font-size: 0.85rem;
  opacity: 0.8;
  transition: all 0.2s ease;
  text-transform: none;
  letter-spacing: 0.3px;
}

.quick-link-btn:hover {
  opacity: 1;
}

/* Mobile styles */
@media (max-width: 767px) {
  .footer-name {
    font-size: 1rem;
  }
  
  .social-btn {
    transform: scale(0.9);
  }
  
  .copyright-text {
    font-size: 0.8rem;
  }
}
</style>