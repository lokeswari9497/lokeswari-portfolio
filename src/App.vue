<script setup lang="ts">
import Home from './views/Home.vue'
import Header from './components/Header.vue'
import HeroSection from './components/HeroComponent.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <v-app>
    <Header />
    <HeroSection />
    <Home />
    <Footer />
  </v-app>
</template>

<style>
body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
  color: #2c2c2c;
  font-size: 18px;
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  line-height: 1.5;
}
#app-root {
  background-color: #efefef;
}
.v-application__wrap {
  max-width: 1440px !important;
  margin: auto;
  padding: 0 16px;
}
h1, h2, h3, h4, h5, h6 {
  word-break: break-word;
  line-height: 1.2;
}
button {
  font-size: 1rem;
  white-space: nowrap;
}
@media (max-width: 600px) {
  body {
    font-size: 14px;
  }
  .v-application__wrap {
    padding: 0 12px;
  }
  h1 {
    font-size: 1.75rem;
  }
  h2 {
    font-size: 1.4rem;
  }
  .v-btn {
    font-size: 0.9rem;
    padding: 8px 16px !important;
  }
  .hero-section {
    padding-top: 100px !important;
    text-align: center;
  }
  .text-justify {
    text-align: left !important; /* Justify doesn't work well on mobile */
  }
}
</style>
