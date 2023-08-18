<script setup>
defineProps({
  fieldname: {
    type: String,
    required: true,
  },
  label: {
    type: String,
    required: true,
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
    default: false,
  }
})
</script>

<template>
  <div>
    <label :for="fieldname">{{ label }}</label>
    <input v-if="!isArea" :type="type" :name="fieldname" :placeholder="placeholder">
    <textarea  v-else :name="fieldname" :placeholder="placeholder"></textarea>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
}

label {
  font-weight: 700;
  font-size: 0.7em;
  margin-bottom: 8px;
}

input {
  font-size: 0.9em;
  border: unset;
  border-radius: 8px;
  height: 3.5em;
  padding: 0 1em;
}

input::placeholder {
  color: rgb(191, 190, 190);
}

textarea {
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