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

/* App layout */
#app-root {
  background-color: #efefef;
}
/* vuetify default app structure doesn't support max-width, centered layouts */
/* https://github.com/vuetifyjs/vuetify/issues/4267 */
.v-application__wrap {
  max-width: 1440px !important;
  margin: auto;
}
</style>
