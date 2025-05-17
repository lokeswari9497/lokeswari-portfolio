<template>
  <v-container class="pt-16 mt-16">
    <section id="contact" class="pt-16 mt-10 mb-12">
      <v-card elevation="8" class="pa-8">
        <v-card-text>
            <h1 class="text-center">Contact Me</h1>
            <v-row no-gutters>
            <!-- Left Column: Form -->
                <v-col cols="12" md="5" class="px-4 py-2">
                <h4>Do not hesitate to contact me</h4>
                <form ref="contactForm" @submit.prevent="sendEmail">
                    <v-text-field
                    v-model="form.user_name"
                    placeholder="Name"
                    required
                    density="compact"
                    variant="outlined"
                    ></v-text-field>

                    <v-text-field
                    v-model="form.user_subject"
                    placeholder="Subject"
                    required
                    density="compact"
                    variant="outlined"
                    ></v-text-field>

                    <v-text-field
                    v-model="form.user_email"
                    placeholder="Email"
                    type="email"
                    required
                    density="compact"
                    variant="outlined"
                    ></v-text-field>

                    <v-textarea
                    v-model="form.message"
                    placeholder="Message"
                    required
                    density="compact"
                    variant="outlined"
                    ></v-textarea>

                    <v-btn type="submit" color="success">Send</v-btn>
                </form>
                </v-col>

                <!-- Right Column: Contact Info -->
                <v-col cols="12" md="5" class="px-4 py-2">
                <p><strong>Address:</strong> Berlin, Germany</p>
                <p><strong>Phone:</strong> +49 176 569 63942</p>
                <p><strong>Email:</strong> lokeswari.loke159@gmail.com</p>
                </v-col>
          </v-row>
        </v-card-text>
      </v-card>
    </section>
  </v-container>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import emailjs from 'emailjs-com'

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
  if (!contactForm.value) return

  emailjs
    .send(serviceId, templateId, contactForm.value, publicKey)
    .then(
      () => {
        alert('Message sent successfully!')
        resetForm()
      },
      (error) => {
        alert('Failed to send message: ' + error.text)
      }
    )
}
</script>
<style scoped>
.v-row {
    text-align: center;
}
h1 {
    text-align: center;
    font-size: 28px;
}
</style>
