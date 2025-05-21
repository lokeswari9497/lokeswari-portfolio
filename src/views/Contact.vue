<template>
  <v-container class="contact-container">
    <section id="contact" class="contact-section">
      <v-card elevation="8" class="contact-card">
        <v-card-text>
          <h1 class="contact-title">Contact Me</h1>
          
          <v-row class="contact-row">
            <!-- Left Column: Form -->
            <v-col cols="12" md="6" class="form-column">
              <h2 class="form-title">Do not hesitate to contact me</h2>
              
              <form ref="contactForm" @submit.prevent="sendEmail" class="contact-form">
                <v-text-field
                  v-model="form.user_name"
                  placeholder="Name"
                  required
                  density="compact"
                  variant="outlined"
                  class="form-field"
                  :class="{ 'mb-4': isMobile }"
                ></v-text-field>

                <v-text-field
                  v-model="form.user_subject"
                  placeholder="Subject"
                  required
                  density="compact"
                  variant="outlined"
                  class="form-field"
                  :class="{ 'mb-4': isMobile }"
                ></v-text-field>

                <v-text-field
                  v-model="form.user_email"
                  placeholder="Email"
                  type="email"
                  required
                  density="compact"
                  variant="outlined"
                  class="form-field"
                  :class="{ 'mb-4': isMobile }"
                ></v-text-field>

                <v-textarea
                  v-model="form.message"
                  placeholder="Message"
                  required
                  density="compact"
                  variant="outlined"
                  auto-grow
                  class="form-field message-field"
                  :class="{ 'mb-4': isMobile }"
                  rows="4"
                ></v-textarea>

                <div class="submit-container">
                  <v-btn 
                    type="submit" 
                    color="success" 
                    class="submit-button"
                    :block="isMobile"
                    :loading="isSubmitting"
                    :disabled="isSubmitting"
                  >
                    Send Message
                  </v-btn>
                </div>
                
                <!-- Success message -->
                <v-alert
                  v-if="showSuccessMessage"
                  type="success"
                  variant="tonal"
                  class="mt-4"
                  closable
                >
                  Your message has been sent successfully! I'll get back to you soon.
                </v-alert>
                
                <!-- Error message -->
                <v-alert
                  v-if="errorMessage"
                  type="error"
                  variant="tonal"
                  class="mt-4"
                  closable
                >
                  {{ errorMessage }}
                </v-alert>
              </form>
            </v-col>

            <!-- Right Column: Contact Info -->
            <v-col cols="12" md="5" class="info-column">
              <div class="contact-info">
                <h3 class="info-title">Contact Information</h3>
                
                <div class="info-item">
                  <v-icon color="#378C3F" class="info-icon">mdi-map-marker</v-icon>
                  <div class="info-text">
                    <strong>Address:</strong>
                    <p>Berlin, Germany</p>
                  </div>
                </div>
                
                <div class="info-item">
                  <v-icon color="#378C3F" class="info-icon">mdi-phone</v-icon>
                  <div class="info-text">
                    <strong>Phone:</strong>
                    <p>+49 176 569 63942</p>
                  </div>
                </div>
                
                <div class="info-item">
                  <v-icon color="#378C3F" class="info-icon">mdi-email</v-icon>
                  <div class="info-text">
                    <strong>Email:</strong>
                    <p>lokeswari.loke159@gmail.com</p>
                  </div>
                </div>
                
                <div class="social-links">
                  <a href="https://github.com/lokeswari9497" target="_blank" class="social-link">
                    <v-icon color="#333">mdi-github</v-icon>
                  </a>
                  <a href="https://www.linkedin.com/in/lokeswari-m/" target="_blank" class="social-link">
                    <v-icon color="#0077B5">mdi-linkedin</v-icon>
                  </a>
                </div>
              </div>
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>
    </section>
  </v-container>
</template>

<script lang="ts" setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
import emailjs from 'emailjs-com'

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

interface ContactForm {
  user_name: string
  user_subject: string
  user_email: string
  message: string
}

const form = ref<ContactForm>({
  user_name: '',
  user_subject: '',
  user_email: '',
  message: '',
})

const contactForm = ref<HTMLFormElement | null>(null)
const isSubmitting = ref(false)
const showSuccessMessage = ref(false)
const errorMessage = ref('')

const resetForm = () => {
  form.value.user_name = ''
  form.value.user_subject = ''
  form.value.user_email = ''
  form.value.message = ''
}

// ENV variables
const serviceId = import.meta.env.VITE_EMAILJS_SERVICE_ID
const templateId = import.meta.env.VITE_EMAILJS_TEMPLATE_ID
const publicKey = import.meta.env.VITE_EMAILJS_PUBLIC_KEY

const sendEmail = () => {
  isSubmitting.value = true
  errorMessage.value = ''
  showSuccessMessage.value = false

  // Create template parameters from form data
  const templateParams = {
    from_name: form.value.user_name,
    subject: form.value.user_subject,
    reply_to: form.value.user_email,
    message: form.value.message
  }

  emailjs
    .send(serviceId, templateId, templateParams, publicKey)
    .then(
      () => {
        showSuccessMessage.value = true
        resetForm()
        setTimeout(() => {
          showSuccessMessage.value = false
        }, 5000)
      },
      (error) => {
        errorMessage.value = 'Failed to send message: ' + (error.text || 'Please try again later')
      }
    )
    .finally(() => {
      isSubmitting.value = false
    })
}
</script>
<style scoped>
/* Container styles */
.contact-container {
  padding: 2rem 1rem;
  margin-top: 2rem;
}

.contact-section {
  margin-bottom: 3rem;
}

.contact-card {
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

/* Title styles */
.contact-title {
  text-align: center;
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 2rem;
  color: #333;
}

.form-title {
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
  color: #378C3F;
  font-weight: 600;
}

/* Form styles */
.contact-form {
  margin-bottom: 1.5rem;
}

.form-field {
  margin-bottom: 1rem;
  transition: all 0.3s ease;
}

.form-field:focus {
  border-color: #378C3F;
}

.message-field {
  min-height: 120px;
}

.submit-container {
  display: flex;
  justify-content: flex-start;
  margin-top: 1rem;
}

.submit-button {
  font-weight: 600;
  letter-spacing: 0.5px;
  padding: 0.5rem 2rem;
  transition: all 0.3s ease;
}

.submit-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

/* Contact info styles */
.info-column {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.contact-info {
  padding: 1.5rem;
  background-color: #f9f9f9;
  border-radius: 8px;
  height: 100%;
}

.info-title {
  font-size: 1.3rem;
  margin-bottom: 1.5rem;
  color: #378C3F;
  font-weight: 600;
}

.info-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 1.25rem;
}

.info-icon {
  margin-right: 1rem;
  margin-top: 0.25rem;
}

.info-text {
  flex: 1;
}

.info-text strong {
  display: block;
  margin-bottom: 0.25rem;
  color: #333;
}

.info-text p {
  margin: 0;
  color: #555;
}

/* Social links */
.social-links {
  display: flex;
  gap: 1rem;
  margin-top: 2rem;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #f0f0f0;
  transition: all 0.3s ease;
}

.social-link:hover {
  transform: translateY(-3px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

/* Responsive styles */
@media (max-width: 767px) {
  .contact-container {
    padding: 1.5rem 1rem;
  }
  
  .contact-title {
    font-size: 1.75rem;
    margin-bottom: 1.5rem;
  }
  
  .form-title, .info-title {
    font-size: 1.25rem;
    text-align: center;
  }
  
  .form-column {
    margin-bottom: 2rem;
  }
  
  .submit-container {
    justify-content: center;
  }
  
  .info-column {
    padding-top: 1rem;
  }
  
  .contact-info {
    padding: 1.25rem;
  }
  
  .info-item {
    margin-bottom: 1rem;
  }
  
  .social-links {
    justify-content: center;
  }
}

@media (min-width: 768px) {
  .contact-container {
    padding: 3rem;
  }
  
  .contact-card {
    padding: 1rem;
  }
  
  .form-column {
    padding-right: 2rem;
  }
  
  .info-column {
    padding-left: 2rem;
  }
}

@media (min-width: 1024px) {
  .contact-container {
    padding: 4rem;
  }
}
</style>
