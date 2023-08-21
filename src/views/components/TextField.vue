<script setup>
defineProps({
  fieldname: {
    type: String,
    required: true
  },
  label: {
    type: String,
    required: true
  },
  placeholder: {
    type: String,
    required: true
  },
  type: {
    type: String,
    default: 'text'
  },
  isArea: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
  <div>
    <label :for="fieldname">{{ label }}</label>
    <input v-if="!isArea" id="input" :type="type" :name="fieldname" :placeholder="placeholder">
    <textarea  v-else :name="fieldname" :placeholder="placeholder"></textarea>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
}

label {
  color: var(--color-primary);
  font-weight: 700;
  font-size: 0.75em;
  margin-bottom: 0.4em;
}

input {
  background-color: var(--color-neutral-100);
  font-size: 0.9em;
  border: unset;
  border-radius: 8px;
  height: 3.5em;
  padding: 0 1em;
  font-family: 'Raleway';
  font-weight: 500;
}

input::placeholder {
  color: rgb(191, 190, 190);
}

textarea {
  background-color: var(--color-neutral-100);
  height: 12em;
  border: unset;
  border-radius: 8px;
  padding: 1em 0 1em 1em;
  font-family: 'Raleway';
  font-weight: 500;
  font-size: 0.9em;
}

textarea::placeholder {
  color: rgb(191, 190, 190);
}

</style>
