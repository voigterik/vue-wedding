<script setup>
import { ref, watch } from "vue";

const formData = ref({
  name: "",
  email: "",
  attending: null,
  guests: 1,
  guestNames: [""],
  dietaryRestrictions: "",
  message: "",
});

const submitted = ref(false);

// Watch for changes in guest count and adjust guestNames array
watch(
  () => formData.value.guests,
  (newCount) => {
    const currentLength = formData.value.guestNames.length;

    if (newCount > currentLength) {
      // Add more empty strings
      for (let i = currentLength; i < newCount; i++) {
        formData.value.guestNames.push("");
      }
    } else if (newCount < currentLength) {
      // Remove excess names
      formData.value.guestNames = formData.value.guestNames.slice(0, newCount);
    }
  },
);

function handleSubmit() {
  // console.log("Form submitted:", formData.value);
  submitted.value = true;
}
</script>

<template>
  <section class="rsvp">
    <div id="rsvp" class="anchor"></div>
    <h2>RSVP</h2>
    <div v-if="!submitted" class="form-container">
      <p>Please let us know if you can make it to our special day!</p>
      <form @submit.prevent="handleSubmit">
        <div class="form-group">
          <label for="name">Full Name *</label>
          <input
            type="text"
            id="name"
            v-model="formData.name"
            required
            placeholder="John & Jane Doe"
          />
        </div>
        <div class="form-group">
          <label for="email">Email *</label>
          <input
            type="email"
            id="email"
            v-model="formData.email"
            required
            placeholder="your@email.com"
          />
        </div>
        <div class="form-group">
          <label>Will you be attending? *</label>
          <div class="radio-group">
            <label class="radio-label">
              <input
                type="radio"
                name="attending"
                :value="true"
                v-model="formData.attending"
                required
              />
              <span>Yes, I'll be there!</span>
            </label>
            <label class="radio-label">
              <input
                type="radio"
                name="attending"
                :value="false"
                v-model="formData.attending"
                required
              />
              <span>Sorry, I can't make it</span>
            </label>
          </div>
        </div>
        <div v-if="formData.attending" class="form-group">
          <label for="guests">Number of Guests *</label>
          <input
            type="number"
            id="guests"
            v-model.number="formData.guests"
            min="1"
            max="5"
            required
          />
        </div>
        <div v-if="formData.attending && formData.guests > 0" class="form-group">
          <label>Guest Names *</label>
          <div class="guest-names">
            <input
              v-for="(guest, index) in formData.guestNames"
              :key="index"
              type="text"
              v-model="formData.guestNames[index]"
              :placeholder="`Guest ${index + 1} Name`"
              required
              class="guest-input"
            />
          </div>
        </div>
        <div v-if="formData.attending" class="form-group">
          <label for="dietary">Dietary Restrictions</label>
          <input
            type="text"
            id="dietary"
            v-model="formData.dietaryRestrictions"
            placeholder="Vegetarian, allergies, etc."
          />
        </div>
        <div class="form-group">
          <label for="message">Message (optional)</label>
          <textarea
            id="message"
            v-model="formData.message"
            rows="4"
            placeholder="Share your thoughts or special requests..."
          ></textarea>
        </div>
        <button type="submit" class="submit-btn">Submit RSVP</button>
      </form>
    </div>
    <div v-else class="thank-you">
      <h3>Thank You!</h3>
      <p v-if="formData.attending">We're so excited to celebrate with you! 🎉</p>
      <p v-else>We'll miss you, but thank you for letting us know. ❤️</p>
    </div>
  </section>
</template>

<style scoped>
.rsvp {
  position: relative;
  padding: 2rem;
  text-align: center;
}

h2 {
  margin-bottom: 3rem;
}

.form-container {
  max-width: 600px;
  margin: 0 auto;
}

.form-container > p {
  margin-bottom: 2rem;
  font-size: 1.1rem;
}

form {
  text-align: left;
}

.form-group {
  margin-bottom: 1.5rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: var(--font-semi-bold);
  color: var(--color-secondary);
}

input[type="text"],
input[type="email"],
input[type="number"],
textarea {
  width: 100%;
  padding: 0.75rem;
  border: 2px solid var(--color-primary);
  border-radius: 8px;
  font-family: "Lato", sans-serif;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: var(--color-secondary);
}

.guest-names {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.guest-input {
  width: 100%;
}

.radio-group {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.radio-label {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem;
  border: 2px solid var(--color-primary);
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.radio-label:hover {
  background: var(--color-blush-white);
}

.radio-label input[type="radio"] {
  width: 20px;
  height: 20px;
  cursor: pointer;
}

.radio-label span {
  font-weight: normal;
}

.submit-btn {
  width: 100%;
  padding: 1rem 2rem;
  background: var(--color-primary);
  color: white;
  border: none;
  border-radius: 8px;
  font-family: "Lato", sans-serif;
  font-size: 1.1rem;
  font-weight: var(--font-semi-bold);
  cursor: pointer;
  transition: background 0.3s ease;
}

.submit-btn:hover {
  background: var(--color-secondary);
}

.thank-you {
  max-width: 600px;
  margin: 0 auto;
  padding: 3rem;
  background: var(--color-blush-white);
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.thank-you h3 {
  color: var(--color-secondary);
  margin-bottom: 1rem;
}

.thank-you p {
  font-size: 1.2rem;
  margin: 1rem 0;
}

@media (max-width: 768px) {
  .form-container {
    padding: 0 1rem;
  }
}
</style>
