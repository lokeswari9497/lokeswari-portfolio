<template>
    <v-container class="main-container" :class="{ 'pt-10 pt-md-16 mt-10 mt-md-16': true }">
        <section id="about" class="section-container">
            <v-card elevation="16" class="section-card">
                <v-card-text>
                    <v-row class="mt-6">
                        <!-- Left Column: Introduction -->
                        <v-col cols="12" md="5" sm="12" class="px-4 py-2">
                            <h2 class="section-title">About</h2>
                            <p class="section-text">
                                Hi! I'm Lokeswari Madhusudhana. I'm a front-end developer and a UI/UX designer.
                            </p>
                            <p class="section-text">
                                I'm a passionate developer with 6+ years of experience working with Vue, React,
                                and modern front-end tooling. I'm constantly improving my craft and excited by
                                new challenges and technologies. Proven track record in delivering
                                performant, accessible, and maintainable frontend systems in fast-paced environments.
                            </p>
                        </v-col>
                        <v-spacer class="d-none d-md-flex"></v-spacer>
                        <!-- Right Column: Basic Info -->
                        <v-col cols="12" md="5" sm="12" class="px-4 py-2">
                            <h2 class="section-title">Basic Information</h2>
                            <div class="info-item">
                                <strong>Age:</strong> <span>28 years old</span>
                            </div>
                            <div class="info-item">
                                <strong>E-mail:</strong> <span>lokeswari.loke159@gmail.com</span>
                            </div>
                            <div class="info-item">
                                <strong>Phone:</strong> <span>+49 176 569 63942</span>
                            </div>
                            <div class="info-item">
                                <strong>Address:</strong> <span>Berlin, Germany</span>
                            </div>
                            <div class="info-item">
                                <strong>Languages:</strong> <span>English, German, Telugu</span>
                            </div>
                        </v-col>
                    </v-row>
                </v-card-text>
            </v-card>
        </section>
    </v-container>

    <v-container class="main-container pt-16 mt-16">
        <section id="skills" class="section-container">
            <h2 class="section-title text-center">Professional Skills</h2>
            <v-card elevation="16" class="section-card">
                <v-card-text>
                    <!-- Desktop view: normal layout -->
                    <div v-if="!isMobile" class="skills-grid">
                        <div class="skill-category">
                            <h3 class="skill-title">Frontend</h3>
                            <div class="skill-chips">
                                <v-chip v-for="skill in frontendSkills" :key="skill" class="skill-chip">
                                    {{ skill }}
                                </v-chip>
                            </div>
                        </div>

                        <div class="skill-category">
                            <h3 class="skill-title">Backend</h3>
                            <div class="skill-chips">
                                <v-chip v-for="skill in backendSkills" :key="skill" class="skill-chip">
                                    {{ skill }}
                                </v-chip>
                            </div>
                        </div>

                        <div class="skill-category">
                            <h3 class="skill-title">Testing</h3>
                            <div class="skill-chips">
                                <v-chip v-for="skill in testingSkills" :key="skill" class="skill-chip">
                                    {{ skill }}
                                </v-chip>
                            </div>
                        </div>

                        <div class="skill-category">
                            <h3 class="skill-title">Tools & DevOps</h3>
                            <div class="skill-chips">
                                <v-chip v-for="skill in toolsSkills" :key="skill" class="skill-chip">
                                    {{ skill }}
                                </v-chip>
                            </div>
                        </div>

                        <div class="skill-category">
                            <h3 class="skill-title">Project Management</h3>
                            <div class="skill-chips">
                                <v-chip class="skill-chip">Jira</v-chip>
                                <v-chip class="skill-chip">Confluence</v-chip>
                            </div>
                        </div>

                        <div class="skill-category">
                            <h3 class="skill-title">Design & Prototyping</h3>
                            <div class="skill-chips">
                                <v-chip class="skill-chip">Figma</v-chip>
                            </div>
                        </div>
                    </div>

                    <!-- Mobile view: accordion-style layout -->
                    <div v-else class="skills-accordion">
                        <div v-for="(category, index) in skillCategories" :key="index" class="skill-category-mobile">
                            <h3 class="skill-title-mobile">{{ category.title }}</h3>
                            <div class="skill-chips-mobile">
                                <v-chip v-for="skill in category.skills" :key="skill" class="skill-chip-mobile">
                                    {{ skill }}
                                </v-chip>
                            </div>
                        </div>
                    </div>
                </v-card-text>
            </v-card>
        </section>
    </v-container>

    <v-container class="main-container pt-16 mt-16">
        <section id="experience" class="section-container">
            <h2 class="section-title text-center">Professional Experiences</h2>
            
            <div class="experience-cards">
                <!-- Experience 1 -->
                <v-card class="experience-card" :class="{ 'outlined': true, 'rounded-0': true }">
                    <v-card-text class="pa-0">
                        <div class="experience-layout">
                            <!-- Left Column -->
                            <div class="experience-header">
                                <h3 class="experience-title">Senior Web Developer</h3>
                                <p class="experience-company">neotiv GmbH, Berlin</p>
                                <p class="experience-period">Apr 2023 – Present</p>
                            </div>

                            <!-- Right Column -->
                            <div class="experience-content">
                                <p class="experience-description">
                                    As a Senior Web Developer, I led the successful migration of a complex web portal from Vue 2 to Vue 3, integrating Vuetify 3 and optimizing the build pipeline with Vite to enhance performance and developer efficiency. I played a key role in delivering impactful features, refining UI components, and improving maintainability through proactive refactoring and test coverage expansion. Working closely with cross-functional teams, I ensured smooth API integration, high-quality releases, and contributed actively to code reviews, fostering a collaborative and high-performing development culture.
                                </p>
                                <p class="experience-tech"><b>Technologies & Environment:</b> Vue 3, Vuetify 3, Vite, TypeScript, Jest, GitLab CI/CD, Docker, REST APIs, Agile (Scrum), Figma</p>
                            </div>
                        </div>
                    </v-card-text>
                </v-card>

                <!-- Experience 2 -->
                <v-card elevation="16" class="experience-card">
                    <v-card-text class="pa-0">
                        <div class="experience-layout">
                            <!-- Left Column -->
                            <div class="experience-header">
                                <h3 class="experience-title">Senior Software Engineer</h3>
                                <p class="experience-company">HCL Technologies Gmbh, Germany</p>
                                <p class="experience-period">Jun 2021 – Mar 2023</p>
                            </div>

                            <!-- Right Column -->
                            <div class="experience-content">
                                <p class="experience-description">
                                    As a Frontend Engineer, I played a pivotal role in developing a back-office loan processing application, streamlining the risk assessment process for underwriters using the Vue.js framework. I delivered key user-facing features that replaced manual workflows with dynamic, scalable interfaces. I was also involved in integrating backend services through an API gateway built with Node.js, and took full ownership of the development lifecycle—from implementation to CI/CD deployment and production release. My contributions included optimizing performance through Micro Frontends, creating reusable components, and contributing to architectural decisions to support scalability and maintainability.
                                </p>
                                <p class="experience-tech"><b>Technologies & Environment:</b> Vue.js, Node.js, JavaScript, Micro Frontends, REST APIs, GitLab CI/CD, Agile (Scrum), API Gateway, Webpack, Docker</p>
                            </div>
                        </div>
                    </v-card-text>
                </v-card>

                <!-- Experience 3 -->
                <v-card elevation="16" class="experience-card">
                    <v-card-text class="pa-0">
                        <div class="experience-layout">
                            <!-- Left Column -->
                            <div class="experience-header">
                                <h3 class="experience-title">Software Engineer</h3>
                                <p class="experience-company">HCL Technologies, Bangalore</p>
                                <p class="experience-period">May 2019 – May 2021</p>
                            </div>

                            <!-- Right Column -->
                            <div class="experience-content">
                                <p class="experience-description">
                                    As part of ING's Maggie program, I contributed to the development of a harmonized multi-country retail banking platform (Rubik), aimed at delivering 80% feature commonality across the countries. Selected to work onsite in Madrid for my front-end expertise and hackathon performance, I took on dual roles as Scrum Master and Proxy Product Owner, driving timely delivery and mentoring team craftsmanship. I was instrumental in developing front-end interfaces using a custom internal framework (Genoma) built on Backbone.js, Stylus, Dust.js, jQuery, and Node.js. My responsibilities spanned sprint planning, development, client-facing sprint reviews, and ensuring alignment with the program's harmonization goals.
                                </p>
                                <p class="experience-tech"><b>Technologies & Environment:</b> Backbone.js, Node.js, Stylus, Dust.js, jQuery, Genoma (custom framework), Agile (Scrum), Jira, Jenkins</p>
                            </div>
                        </div>
                    </v-card-text>
                </v-card>

                <!-- Experience 4 -->
                <v-card elevation="16" class="experience-card">
                    <v-card-text class="pa-0">
                        <div class="experience-layout">
                            <!-- Left Column -->
                            <div class="experience-header">
                                <h3 class="experience-title">Software Engineer</h3>
                                <p class="experience-company">HCL Technologies, Bangalore</p>
                                <p class="experience-period">Aug 2018 – Apr 2019</p>
                            </div>

                            <!-- Right Column -->
                            <div class="experience-content">
                                <p class="experience-description">
                                    Contributed to the development of BASA, a client-facing advisory platform that captures financial goals and life-phase details to recommend tailored investment products across multiple categories including wealth creation, security accounts, and portfolio solutions. I was responsible for implementing new user-facing features in the Security Account module using React.js and Bootstrap, while also ensuring high-quality code delivery. Played a key role in defect resolution during critical release phases and gained practical experience with modern CI/CD and project tracking tools.
                                </p>
                                <p class="experience-tech"><b>Technologies & Environment:</b> React.js, Redux, Bootstrap, Bitbucket, TeamCity, Jira</p>
                            </div>
                        </div>
                    </v-card-text>
                </v-card>
            </div>
        </section>
    </v-container>

    <v-container class="main-container pt-16 mt-16">
        <section id="education" class="section-container">
            <h2 class="section-title text-center">Training - Education</h2>
            <v-card elevation="16" class="section-card">
                <v-card-text class="pa-0">
                    <div class="education-layout">
                        <!-- Left Column -->
                        <div class="education-header">
                            <h3 class="education-title">Bachelor's degree</h3>
                            <p class="education-period">Aug 2014 – May 2018</p>
                        </div>

                        <!-- Right Column -->
                        <div class="education-content">
                            <h4 class="education-degree">Bachelor of Technology in Electronics and Communication Engineering</h4>
                            <p class="education-institution">Sreenivasa Institute of Technology and Management Studies, Andhra Pradesh</p>
                        </div>
                    </div>
                </v-card-text>
            </v-card>
        </section>
    </v-container>
    
    <Contact />
</template>

<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue'
import Contact from './Contact.vue'

// Responsive design
const windowWidth = ref(window.innerWidth)
const isMobile = computed(() => windowWidth.value < 768)

const updateWindowWidth = () => {
  windowWidth.value = window.innerWidth
}

onMounted(() => {
  window.addEventListener('resize', updateWindowWidth)
  updateWindowWidth() // Ensure initial width is set
})

onUnmounted(() => {
  window.removeEventListener('resize', updateWindowWidth)
})

// Skills data
const frontendSkills = ['Vue 3', 'Vite', 'Vuetify 3', 'Vuex', 'React.js', 'TypeScript']
const backendSkills = ['Node.js', 'REST APIs', 'Java', 'C#', 'SQL']
const testingSkills = ['Jest', 'Cypress', 'Mocha', 'Chai', 'Sinon']
const toolsSkills = ['GitLab CI/CD', 'Github', 'Docker', 'Jenkins', 'Azure DevOps']

// For mobile view - organized categories
const skillCategories = computed(() => [
  { title: 'Frontend', skills: frontendSkills },
  { title: 'Backend', skills: backendSkills },
  { title: 'Testing', skills: testingSkills },
  { title: 'Tools & DevOps', skills: toolsSkills },
  { title: 'Project Management', skills: ['Jira', 'Confluence'] },
  { title: 'Design & Prototyping', skills: ['Figma'] }
])
</script>

<style scoped>
/* General layout */
.main-container {
  padding: 2rem 1rem;
  transition: all 0.3s ease;
}

.section-container {
  scroll-margin-top: 80px;
  margin-bottom: 3rem;
}

.section-card {
  border-radius: 8px;
  overflow: hidden;
  transition: all 0.3s ease;
  padding: 1rem;
}

.section-title {
  font-weight: 700;
  margin-bottom: 1.5rem;
  color: #333;
  font-size: 1.5rem;
}

.section-text {
  margin-bottom: 1rem;
  line-height: 1.6;
}

/* About section */
.info-item {
  margin-bottom: 0.75rem;
  display: flex;
  flex-wrap: wrap;
}

.info-item strong {
  min-width: 100px;
  margin-right: 0.5rem;
}

/* Skills section */
.skills-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2rem;
}

.skill-category {
  margin-bottom: 1.5rem;
}

.skill-title {
  font-weight: 600;
  margin-bottom: 0.75rem;
  color: #378C3F;
}

.skill-chips {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.skill-chip {
  margin: 0.25rem;
  background-color: #f5f5f5;
  transition: all 0.3s ease;
}

.skill-chip:hover {
  background-color: #e0e0e0;
  transform: translateY(-2px);
}

/* Mobile skills */
.skills-accordion {
  display: flex;
  flex-direction: column;
}

.skill-category-mobile {
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #eee;
}

.skill-title-mobile {
  font-weight: 600;
  margin-bottom: 1rem;
  color: #378C3F;
}

.skill-chips-mobile {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.skill-chip-mobile {
  margin: 0.25rem;
  background-color: #f5f5f5;
}

/* Experience section */
.experience-cards {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.experience-card {
  border-radius: 8px;
  overflow: hidden;
  transition: all 0.3s ease;
}

.experience-layout {
  display: flex;
  flex-direction: column;
}

.experience-header {
  background-color: #378C3F;
  color: white;
  padding: 1.5rem;
  text-align: center;
}

.experience-title {
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.experience-company {
  margin-bottom: 0.25rem;
  font-size: 0.9rem;
}

.experience-period {
  font-size: 0.85rem;
  opacity: 0.9;
}

.experience-content {
  padding: 1.5rem;
}

.experience-description {
  margin-bottom: 1rem;
  line-height: 1.6;
}

.experience-tech {
  font-size: 0.9rem;
  color: #555;
}

/* Education section */
.education-layout {
  display: flex;
  flex-direction: column;
}

.education-header {
  background-color: #378C3F;
  color: white;
  padding: 1.5rem;
  text-align: center;
}

.education-title {
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.education-period {
  font-size: 0.85rem;
  opacity: 0.9;
}

.education-content {
  padding: 1.5rem;
}

.education-degree {
  margin-bottom: 0.5rem;
  font-weight: 600;
}

.education-institution {
  color: #555;
}

/* Responsive styles */
@media (min-width: 768px) {
  .main-container {
    padding: 3rem;
  }
  
  .section-card {
    padding: 2rem;
  }
  
  .section-title {
    font-size: 1.75rem;
  }
  
  .experience-layout, .education-layout {
    flex-direction: row;
  }
  
  .experience-header, .education-header {
    width: 25%;
    padding: 2rem 1.5rem;
  }
  
  .experience-content, .education-content {
    width: 75%;
    padding: 2rem;
  }
}

@media (min-width: 1024px) {
  .main-container {
    padding: 4rem;
  }
  
  .skills-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>