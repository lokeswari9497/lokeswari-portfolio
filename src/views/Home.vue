<template>
    <v-container class="pt-16 mt-16">
        <section id="about" class="mt-10 mb-12">
            <v-card elevation="16" class="pa-8">
                <v-card-text>
                    <v-row class="mt-6">
                        <!-- Left Column: Introduction -->
                        <v-col cols="12" md="5" class="px-4 py-2">
                            <h2>About</h2>
                            <p class="text-justify">
                                Hi! I'm Lokeswari Madhusudhana. I'm a front-end developer and a UI/UX designer.
                            </p>
                            <p class="text-justify">
                                I'm a passionate developer with 6+ years of experience working with Vue, React,
                                and modern front-end tooling. I’m constantly improving my craft and excited by
                                new challenges and technologies. Proven track record in delivering
                                performant, accessible, and maintainable frontend systems in fast-paced environments.
                            </p>
                        </v-col>
                        <v-spacer></v-spacer>
                        <!-- Right Column: Basic Info -->
                        <v-col cols="12" md="5" class="px-4 py-2">
                            <h2>Basic Information</h2>
                            <p class="text-left">
                                <strong>Age:</strong>   28 years old
                            </p>
                            <p class="text-left">
                                <strong>E-mail:</strong>   lokeswari.loke159@gmail.com
                            </p>
                            <p class="text-left">
                                <strong>Phone:</strong>   +49 176 569 63942
                            </p>
                            <p class="text-left">
                                <strong>Address:</strong>   Berlin, Germany
                            </p>
                            <p class="text-left">
                                <strong>Languages:</strong>   English, German, Telugu
                            </p>
                        </v-col>
                    </v-row>
                </v-card-text>
            </v-card>
        </section>
    </v-container>
    <v-container class="pt-16 mt-16">
        <section id="skills" class="pt-16 mt-5 mb-12">
            <h2 class="text-center">Professional Skills</h2>
            <v-card elevation="16" class="pa-8">
                <v-card-text>
                    <v-row>
                        <v-col cols="12" md="5">
                            <h3 class="mr-4 mb-0">Frontend</h3>
                            <v-chip v-for="skill in frontendSkills" :key="skill">
                                {{ skill }}
                            </v-chip>
                        </v-col>

                        <v-col cols="12" md="6">
                            <h3 class="mb-2">Backend</h3>
                            <v-chip v-for="skill in backendSkills" :key="skill">
                                {{ skill }}
                            </v-chip>
                        </v-col>

                        <v-col cols="12" md="5" class="mt-4">
                            <h3 class="mb-2">Testing</h3>
                            <v-chip v-for="skill in testingSkills" :key="skill">
                                {{ skill }}
                            </v-chip>
                        </v-col>

                        <v-col cols="12" md="6" class="mt-4">
                            <h3 class="mb-2">Tools & DevOps</h3>
                            <v-chip v-for="skill in toolsSkills" :key="skill">
                                {{ skill }}
                            </v-chip>
                        </v-col>

                        <v-col cols="12" md="5" class="mt-4">
                            <h3 class="mb-2">Project Management</h3>
                            <v-chip>Jira</v-chip>
                            <v-chip>Confluence</v-chip>
                        </v-col>

                        <v-col cols="12" md="6" class="mt-4">
                            <h3 class="mb-2">Design & Prototyping</h3>
                            <v-chip>Figma</v-chip>
                        </v-col>
                    </v-row>
                </v-card-text>
            </v-card>
        </section>
    </v-container>
    <v-container class="pt-16 mt-16">
        <section id="experience" class="pt-16 mt-10 mb-12">
            <h2 class="text-center">Professional Experiences</h2>
            <v-card class="pa-4 outlined" rounded="0">
                <v-card-text>
                    <v-row>
                        <!-- Left Column -->
                        <v-col cols="12" md="3" class="pa-6" style="background-color: #378C3F; color: white;">
                            <h3 class="mb-2">Senior Web Developer</h3>
                            <p class="mb-1">neotiv GmbH, Berlin</p>
                            <p class="mb-0">Apr 2023 – Present</p>
                        </v-col>

                        <!-- Right Column -->
                        <v-col cols="12" md="8" class="pa-6">
                            <p class="pl-4">
                                As a Senior Web Developer, I led the successful migration of a complex web portal from Vue 2 to Vue 3, integrating Vuetify 3 and optimizing the build pipeline with Vite to enhance performance and developer efficiency. I played a key role in delivering impactful features, refining UI components, and improving maintainability through proactive refactoring and test coverage expansion. Working closely with cross-functional teams, I ensured smooth API integration, high-quality releases, and contributed actively to code reviews, fostering a collaborative and high-performing development culture.
                            </p>
                            <p><b>Technologies & Environment:</b>Vue 3, Vuetify 3, Vite, TypeScript, Jest, GitLab CI/CD, Docker, REST APIs, Agile (Scrum), Figma</p>
                        </v-col>
                    </v-row>
                </v-card-text>
            </v-card>
            <v-card elevation="16" class="pa-8">
                <v-card-text>
                    <v-row>
                        <!-- Left Column -->
                        <v-col cols="12" md="3" class="pa-6" style="background-color: #378C3F; color: white;">
                            <h3 class="mb-2">Senior Software Engineer</h3>
                            <p class="mb-1">HCL Technologies Gmbh, Germany</p>
                            <p class="mb-0">Jun 2021 – Mar 2023</p>
                        </v-col>

                        <!-- Right Column -->
                        <v-col cols="12" md="8" class="pa-6">
                            <p class="pl-4">
                                As a Frontend Engineer, I played a pivotal role in developing a back-office loan processing application, streamlining the risk assessment process for underwriters using the Vue.js framework. I delivered key user-facing features that replaced manual workflows with dynamic, scalable interfaces. I was also involved in integrating backend services through an API gateway built with Node.js, and took full ownership of the development lifecycle—from implementation to CI/CD deployment and production release. My contributions included optimizing performance through Micro Frontends, creating reusable components, and contributing to architectural decisions to support scalability and maintainability.
                            </p>
                            <p><b>Technologies & Environment:</b>Vue.js, Node.js, JavaScript, Micro Frontends, REST APIs, GitLab CI/CD, Agile (Scrum), API Gateway, Webpack, Docker</p>
                        </v-col>
                    </v-row>
                </v-card-text>
            </v-card>
            <v-card elevation="16" class="pa-8">
                <v-card-text>
                    <v-row>
                        <!-- Left Column -->
                        <v-col cols="12" md="3" class="pa-6" style="background-color: #378C3F; color: white;">
                            <h3 class="mb-2">Software Engineer</h3>
                            <p class="mb-1">HCL Technologies, Bangalore</p>
                            <p class="mb-0">May 2019 – May 2021</p>
                        </v-col>

                        <!-- Right Column -->
                        <v-col cols="12" md="8" class="pa-6">
                            <p class="pl-4">
                                As part of ING’s Maggie program, I contributed to the development of a harmonized multi-country retail banking platform (Rubik), aimed at delivering 80% feature commonality across the countries. Selected to work onsite in Madrid for my front-end expertise and hackathon performance, I took on dual roles as Scrum Master and Proxy Product Owner, driving timely delivery and mentoring team craftsmanship. I was instrumental in developing front-end interfaces using a custom internal framework (Genoma) built on Backbone.js, Stylus, Dust.js, jQuery, and Node.js. My responsibilities spanned sprint planning, development, client-facing sprint reviews, and ensuring alignment with the program’s harmonization goals.
                            </p>
                            <p><b>Technologies & Environment:</b>Backbone.js, Node.js, Stylus, Dust.js, jQuery, Genoma (custom framework), Agile (Scrum), Jira, Jenkins</p>
                        </v-col>
                    </v-row>
                </v-card-text>
            </v-card>
            <v-card elevation="16" class="pa-8">
                <v-card-text>
                    <v-row>
                        <!-- Left Column -->
                        <v-col cols="12" md="3" class="pa-6" style="background-color: #378C3F; color: white;">
                            <h3 class="mb-2">Software Engineer</h3>
                            <p class="mb-1">HCL Technologies, Bangalore</p>
                            <p class="mb-0">Aug 2018 – Apr 2019</p>
                        </v-col>

                        <!-- Right Column -->
                        <v-col cols="12" md="8" class="pa-6">
                            <p class="pl-4">
                                Contributed to the development of BASA, a client-facing advisory platform that captures financial goals and life-phase details to recommend tailored investment products across multiple categories including wealth creation, security accounts, and portfolio solutions. I was responsible for implementing new user-facing features in the Security Account module using React.js and Bootstrap, while also ensuring high-quality code delivery. Played a key role in defect resolution during critical release phases and gained practical experience with modern CI/CD and project tracking tools.
                            </p>
                            <p><b>Technologies & Environment:</b>React.js, Redux, Bootstrap, Bitbucket, TeamCity, Jira</p>
                        </v-col>
                    </v-row>
                </v-card-text>
            </v-card>
        </section>
    </v-container>
    <v-container class="pt-16 mt-16">
        <section id="education" class="pt-16 mt-10 mb-12">
            <h2 class="text-center">Training - Education</h2>
            <v-card elevation="16" class="pa-8">
                <v-card-text>
                    <v-row>
                        <!-- Left Column -->
                        <v-col cols="12" md="3" class="education pa-6" style="background-color: #378C3F; color: white;">
                            <h3 class="mb-1">Bachelor's degree</h3>
                            <p class="mb-0">Aug 2014 – May 2018</p>
                        </v-col>

                        <!-- Right Column -->
                        <v-col cols="12" md="8" class="pa-6">
                            <h4>Bachelor of Technology in Electronics and Communication Engineering</h4>
                            <p>Sreenivasa Institute of Technology and Management Studies, Andhra Pradesh</p>
                        </v-col>
                    </v-row>
                </v-card-text>
            </v-card>
        </section>
    </v-container>
    <Contact />
</template>
<script setup lang="ts">
import Contact from './Contact.vue'
    const frontendSkills = ['Vue 3', 'Vite', 'Vuetify 3', 'Vuex', 'React.js', 'typescript']
    const backendSkills = ['Node.js', 'REST APIs', 'Java', 'C#', 'SQL']
    const testingSkills = ['Jest', 'Cypress', 'Mocha', 'Chai', 'Sinon']
    const toolsSkills = ['GitLab CI/CD', 'Github', 'Docker', 'Jenkins', 'Azure DevOps']
</script>

<style scoped>
.v-container {
    padding: 5rem;
}
section {
  scroll-margin-top: 150px; /* Useful for scroll-to behavior */
}
.v-chip {
    margin-left: 12px;
}
.v-card {
    margin-bottom: 4rem;
}
.v-row {
    margin: -18px;
}
@media (min-width: 960px) {
    .v-col-md-3 {
        text-align: center;
        padding-top: 32px;
    }
}
.v-col-md-3.v-col-12.education.pa-6 {
    text-align: center;
    padding-top: 16px;
}
</style>