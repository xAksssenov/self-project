<template>
    <NuxtLayout>
        <NuxtPage />
    </NuxtLayout>
</template>

<style lang="scss">
* {
    padding: 0;
    margin: 0;
    font-size: 1rem;
}

input,
textarea {
    user-select: text;
}

html {
    font-size: 62.5%;
    overflow-x: hidden;
    background-color: rgb(24 24 27);
}

body {
    margin: 0;
    font-family: Goldman, sans-serif;
    color: white;
}

h1 {
    font-size: 1.4rem;
}

h2 {
    font-size: 1.3rem;
}

h3 {
    font-size: 1.2rem;
}

h4 {
    font-size: 1.1rem;
}

h5 {
    font-size: 1rem;
}

a {
    text-decoration: none;
    outline: none;
}

input {
    display: block;
    box-sizing: border-box;
    background: none;
    border: none;
    border-radius: 0.15rem;
    outline: none;
    transition: 100ms;
}

button {
    display: block;
    box-sizing: border-box;
    text-align: center;
    background: none;
    border: none;
    border-radius: 0.2rem;
    outline: none;
    cursor: pointer;
    transition: 100ms;
}

ol,
ul {
    list-style: none;
}

.carousel__viewport {
    overflow: visible;
}
</style>
