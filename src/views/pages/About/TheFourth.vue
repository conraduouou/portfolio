<script setup>
import TextField from './../../components/TextField.vue'
</script>

<template>
  <section>
    <form>
      <h2>Want to get in touch?</h2>
      <div>
        <div class="form-name-email">
          <TextField fieldname="name" label="Name" placeholder="Enter your name" />
          <TextField fieldname="email" label="Email" placeholder="Enter your email" type="email"/>
        </div>
        <TextField class="form-message" fieldname="message" label="Message" placeholder="Enter your message" isArea="true"/>
        <button type="button">Submit</button>
      </div>
    </form>
  </section>
</template>

<style scoped>
section {
  padding: var(--section-padding);
  padding-top: 60px;
  padding-bottom: 60px;
}

form {
  border: 2px solid var(--color-primary);
  border-radius: 32px;
  display: flex;
  justify-content: space-between;
  gap: max(24px, 4vw);
  padding: 60px;
}

form>h2 {
  font-weight: 600;
  font-size: 3.5em;
  width: 45%;
  text-align: justify;
  letter-spacing: 0.015em;
}

form>div:nth-child(2) {
  width: 45%;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.form-name-email {
  display: flex;
  justify-content: space-between;
}

.form-name-email div {
  width: 47%;
}

button {
  border: unset;
  padding: 12px 24px;
  background-color: var(--color-primary);
  color: var(--color-background);
  border-radius: 8px;
  transition: background-color 0.2s ease;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  width: min-content;
}

button:hover {
  background-color: var(--color-primary-dark);
}
</style>
