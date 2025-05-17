<template>
  <v-app-bar class="app-header" elevation="5" height="96" scroll-behavior="elevate">
    <v-row no-gutters>
        <v-col>
            <v-app-bar-title>Lokeswari Madhusudhana</v-app-bar-title>
        </v-col>
        <v-col>
            <v-btn
                v-for="link in links"
                :key="link.text"
                :to="link.href"
                class="nav-btn"
                variant="plain"
                @click.prevent="scrollToSection(link.href)"
            >
                {{ link.text }}
            </v-btn>
        </v-col>
    </v-row>
  </v-app-bar>
</template>

<script setup lang="ts">
    const links = [
        { text: 'About', href: '#about' },
        { text: 'Skills', href: '#skills' },
        { text: 'Experience', href: '#experience' },
        { text: 'Contact', href: '#contact' },
    ]

    const scrollToSection = (selector: string): void => {
        const target = document.querySelector(selector)
        if (target) {
            target.scrollIntoView({ behavior: 'smooth', block: 'start' })
        }
    }

</script>

<style scoped>
.app-header {
    width: 100%;
    max-width: 100%;
    background-color: #378C3F !important;
}
.v-toolbar-title {
    color: white;
    font-size: 1.5rem;
    margin-inline-start: 64px;
}
.nav-btn {
  font-weight: 500;
  font-size: 16px;
  margin: 0 12px;
  color: white !important;
  opacity: 1;
  transition: opacity 0.3s ease;
}
</style>
