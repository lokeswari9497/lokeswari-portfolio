<template>
  <section class="hero-section">
    <v-container>
      <v-avatar size="160" class="mb-6">
        <v-img :src="profilePic" alt="Profile Picture" class="profile-image mb-6" />
      </v-avatar>

      <h1 class="mb-2">LOKESWARI MADHUSUDHANA</h1>
      <h2 class="mb-6">
        FRONT-END DEVELOPER · UI/UX DESIGNER
      </h2>

      <div class="d-flex justify-center button-group mb-6">
        <v-btn color="success" class="px-6 py-2" @click="scrollTo('contact')">
          Hire me
        </v-btn>
        <v-btn color="success" class="px-6 py-2" @click="downloadCV">
          Download CV
        </v-btn>
      </div>
    </v-container>
  </section>
</template>

<script setup lang="ts">
import profilePic from '../assets/profile.jpeg'

const scrollTo = (sectionId: string): void => {
  const el = document.getElementById(sectionId)
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' })
  }
}

const downloadCV = (): void => {
  window.open('/cv.pdf', '_blank')
}
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
}
h1, h2 {
  color: white;
}
.profile-image {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  object-fit: contain;
  border: 4px solid black;
}
.button-group > *:not(:last-child) {
  margin-right: 24px;
}
</style>
