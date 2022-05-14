<template>
    <main class="main">
        <h1 class="title">Wordle</h1>
        <p class="text">A Wordle Clone</p>
        <NuxtLink to="/play">Play</NuxtLink>
        <sub>Thank you
            <a href="https://www.kaggle.com/datasets/shamiljamion/wordle-answers" target="_blank">shamiljamion</a>
            for the list of words!
        </sub>
        <sub>Play the official Wordle game
            <a href="https://www.nytimes.com/games/wordle/index.html" target="_blank">
                here
            </a>
        </sub>
    </main>
</template>

<style scoped>
.main {
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}

.title {
    font-size: 4rem;
    text-align: center;
    color: #00DC82;
}

.text {
    font-size: 2rem;
    text-align: center;
    color: #80EEC0;
}
</style>
