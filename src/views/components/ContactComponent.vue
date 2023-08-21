<script setup>
import TextField from './TextField.vue'
</script>

<template>
    <section>
        <h2>Want to get in touch?</h2>
        <form action="#">
            <TextField class="textfield" fieldname="name" label="Name" placeholder="Please enter your name" />
            <TextField class="textfield" fieldname="email" label="Email" placeholder="Please enter your email" />
            <TextField class="textfield" fieldname="message" label="Message" placeholder="Please enter your message"
                :is-area="true" />
            <button type="submit">Submit</button>
        </form>
    </section>
</template>

<style scoped>
section {
    background-color: var(--color-background);
    box-shadow: 0px 6px 8px 0px rgba(60, 60, 60, 0.12);
    border-radius: 1em;
    border: 1.5px solid var(--color-primary);
    padding: 8vw 6vw 10vw 6vw;
}

form {
    display: flex;
    flex-direction: column;
}

h2 {
    font-size: 2em;
    font-weight: 600;
    text-align: center;
    margin-bottom: 1.8em;
}

.textfield {
    margin-bottom: 1.5em;
}

button {
    margin-top: 2.6em;
    color: var(--color-background);
    font-weight: 700;
    font-size: 1em;
    background-color: var(--color-primary-700);
    border: unset;
    border-radius: 0.5em;
    padding: 1em 2.8em;
    align-self: center;
}
</style>
