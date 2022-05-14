<template>
    <main class="main">
        <h1 class="title">
            Play
        </h1>
        <NuxtLink to="/">Home</NuxtLink>
        <!-- <p class="text">
            Press the button below to subtract the two numbers
        </p>
        <input v-model="num1" placeholder="number 1" />
        <input v-model="num2" placeholder="number 2" />
        <button @click="sub(num1, num2)">Subtract</button>
        <p class="text">{{ diff }}</p> -->
    </main>
</template>

<script setup lang="ts">
// const diff = ref(0)
// const num1 = ref(0)
// const num2 = ref(0)

// const sub = (x: number, y: number) => {
//     diff.value = x - y
// }
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
}

.text {
    font-size: 2rem;
    text-align: center;
}
</style>
