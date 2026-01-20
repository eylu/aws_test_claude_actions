<template>
  <div class="contact">
    <h1>Contact Us</h1>
    <p>Get in touch with us using the form below.</p>

    <form @submit.prevent="handleSubmit" class="contact-form">
      <div class="form-group">
        <label for="name">Name:</label>
        <input
          type="text"
          id="name"
          v-model="formData.name"
          required
          placeholder="Enter your name"
        >
      </div>

      <div class="form-group">
        <label for="email">Email:</label>
        <input
          type="email"
          id="email"
          v-model="formData.email"
          required
          placeholder="Enter your email"
        >
      </div>

      <div class="form-group">
        <label for="message">Message:</label>
        <textarea
          id="message"
          v-model="formData.message"
          required
          placeholder="Enter your message"
          rows="5"
        ></textarea>
      </div>

      <button type="submit">Send Message</button>
    </form>

    <div v-if="submitted" class="success-message">
      <p>Thank you for your message! We'll get back to you soon.</p>
    </div>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'

export default {
  name: 'Contact',
  setup() {
    const formData = reactive({
      name: '',
      email: '',
      message: ''
    })

    const submitted = ref(false)

    const handleSubmit = () => {
      console.log('Form submitted:', formData)
      submitted.value = true

      // Reset form after 3 seconds
      setTimeout(() => {
        formData.name = ''
        formData.email = ''
        formData.message = ''
        submitted.value = false
      }, 3000)
    }

    return {
      formData,
      submitted,
      handleSubmit
    }
  }
}
</script>

<style scoped>
.contact {
  max-width: 600px;
  margin: 0 auto;
  padding: 40px 20px;
}

h1 {
  color: #42b983;
  margin-bottom: 10px;
  text-align: center;
}

p {
  text-align: center;
  margin-bottom: 30px;
  font-size: 16px;
}

.contact-form {
  background-color: #f9f9f9;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: 600;
  color: #333;
}

input,
textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 14px;
  font-family: inherit;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #42b983;
}

button {
  width: 100%;
  background-color: #42b983;
  color: white;
  border: none;
  padding: 12px 24px;
  font-size: 16px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #35a372;
}

.success-message {
  margin-top: 20px;
  padding: 15px;
  background-color: #d4edda;
  border: 1px solid #c3e6cb;
  border-radius: 4px;
  text-align: center;
}

.success-message p {
  color: #155724;
  margin: 0;
}

@media (prefers-color-scheme: dark) {
  .contact-form {
    background-color: #333;
  }

  label {
    color: #fff;
  }

  input,
  textarea {
    background-color: #444;
    color: #fff;
    border-color: #555;
  }
}
</style>
