<template>
    <main class="main">
        <h1 class="title">
            Play Wordle
        </h1>
        <div class="triedWords">
            <div v-for="w in triedWords" class="word">
                <div v-for="i in 5" class="char">
                    <span :class="colors[triedWords.indexOf(w)][i - 1]">{{ w[i - 1] }}</span>
                </div>
            </div>
        </div>

        <div v-if="triedWords.length < 6 && !gameOver" class="form">
            <input type="text" placeholder="Enter Word" v-model="word" class="input" />
            <button @click="play(word)" class="button">Check</button>
        </div>

        <p v-if="triedWords.length === 6" class="text">The answer is {{ answer.toUpperCase() }}</p>

        <NuxtLink to="/" class="button">Home</NuxtLink>
    </main>
</template>

<script setup lang="ts">
const WORDS = useWords().value

const answer = ref("")

const word = ref("")
const triedWords = ref([])
const colors = ref([])

const gameOver = ref(false)

onMounted(() => answer.value = WORDS[Math.floor(Math.random() * WORDS.length)])

const play = (guess: string) => {
    if (WORDS.includes(guess.toLowerCase())) {
        triedWords.value.push(guess.toUpperCase())
        word.value = ""

        let color = ""
        let colorsLength = colors.value.length
        colors.value.push([])

        for (let i = 0; i < guess.length; i++) {
            const c = guess[i]
            color = checkChar(guess, c, i)
            colors.value[colorsLength].push(color)
        }

        if (guess.toLowerCase() === answer.value) gameOver.value = true
    } else {
        alert("Invalid guess! Try another word!")
    }
}

const checkChar = (w: string, c: string, i: number) => {
    const index = w.indexOf(c, i)
    if (answer.value.indexOf(c.toLowerCase(), i) === index) return "green"
    else if (answer.value.includes(c.toLowerCase())) return "yellow"
    else return "white"
}
</script>

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

.text,
.char {
    font-size: 2rem;
    text-align: center;
    color: #80EEC0;
    margin: 0 1rem;
}

.char {
    width: 0.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
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
    cursor: pointer;
    background-color: #001F27;
}

.button:hover {
    background-color: #80EEC0;
    color: #001F27;
}

.button:focus {
    outline: none;
    background-color: #80EEC0;
    color: #001F27;
}

.green {
    color: #80EEC0;
}

.yellow {
    color: #fed663;
}

.white {
    color: #fff;
}

.form {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}

.input {
    all: unset;
    background-color: #001F27;
    font-size: 2rem;
    border: 0.3rem solid #80EEC0;
    border-radius: 0.3rem;
    padding: 0.3rem 1rem;
    color: #fff;
    text-align: center;
}

.triedWords {
    min-width: 30vw;
    min-height: 15rem;
    margin: 1rem;
    border: 0.3rem solid #fff
}

.word {
    display: flex;
    align-items: center;
    justify-content: center;
    column-gap: 2rem;
    height: 2rem;
    margin: 0.5rem 0;
}

@media (max-width: 800px) {
    .title {
        font-size: 2rem;
    }

    .text,
    .button,
    .input,
    .char {
        font-size: 1rem;
    }

    .word {
        column-gap: 1rem
    }

    .triedWords {
        min-width: 70vw;
    }
}
</style>
