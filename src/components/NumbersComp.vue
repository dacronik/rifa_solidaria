<script setup>
import { ref } from 'vue';

const numbers = ref([]);

for (let i = 1; i <= 250; i++) {
    numbers.value.push({
        value: i
    });
}

const numerosVendidos = ref([2, 111, 54, 75,22,44,65,123,155,213]);

function isSold(number) {
    return numerosVendidos.value.includes(number);
}
</script>

<template>
    <section class="title">
        <h1>Numeros de Rifa</h1>

    </section>
    <v-container fluid>
        <v-row>
            <v-col v-for="(number, index) in numbers" :key="index" cols="2" sm="3" md="2" lg="1">
                <v-card class="square" :class="{ sold: isSold(number.value) }">
                    <v-card-text class="text-center">{{ number.value }}</v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>


</template>

<style scoped>
.title {
    font-size: 3rem;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    margin: 70px 0 40px;
    font-family: "Monoton";
    font-size: 400;
    color: aliceblue;
}

.title h1 {
    background: #2193b0;
    /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #6dd5ed, #2193b0);
    background: linear-gradient(to right, #6dd5ed, #2193b0);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;

}

.grid {
    display: grid;
    grid-template-columns: repeat(10, 1fr);
    grid-gap: 10px;
}

.square {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    background-color: white;
    color: black;
}

.square.sold {
    background-color: red;
    color: white;
}

.square.unsold {
    background-color: white;
    color: black;
}
</style>