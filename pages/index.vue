<template>
    <main class="main">
        <h1 class="title">A Wordle Clone by
            <a href="https://xyntechx.com/" target="_blank" class="link">Nyx Iskandar</a>
        </h1>
        <p class="text">5 Letters at a Time</p>
        <NuxtLink to="/play" class="button">Play</NuxtLink>
        <footer class="creds">
            <sub>Play the official Wordle game
                <a href="https://www.nytimes.com/games/wordle/index.html" target="_blank" class="link-sub">
                    here
                </a>
            </sub>
        </footer>
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
    margin: 1rem;
}

.text {
    font-size: 2rem;
    text-align: center;
    color: #80EEC0;
    margin: 0 1rem;
}

.creds {
    margin: 0 1rem;
    position: fixed;
    bottom: 10px;
    color: white;
    font-size: 1rem;
    text-align: center;
}

.button {
    color: #80EEC0;
    border: 0.3rem solid #80EEC0;
    border-radius: 0.3rem;
    font-size: 2rem;
    text-decoration: none;
    padding: 0.3rem 1rem;
    margin: 1rem;
    transition: 0.3s;
}

.button:hover {
    background-color: #80EEC0;
    color: #001F27;
}

.link {
    color: #00DC82;
    transition: 0.3s;
}

.link:hover {
    border: 0.3rem solid #00DC82;
    border-radius: 0.5rem;
    text-decoration: none;
    padding: 0.3rem 1rem;
}

.link-sub {
    color: #00DC82;
}

@media (max-width: 800px) {
    .title {
        font-size: 2rem;
    }

    .text,
    .button {
        font-size: 1rem;
    }

    .creds {
        font-size: 0.5rem;
    }
}
</style>
