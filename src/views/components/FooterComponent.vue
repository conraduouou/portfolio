<template>
    <div>
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
    </div>
</template>

<style scoped>
div {
    display: flex;
    gap: max(8vw, 2em);
    justify-content: center;
    align-items: center;
    padding: min(70px, 15vh) 0;
}

a {
    text-decoration: none;
    color: var(--color-neutral-600);
    font-weight: 500;
}
</style>
