<script setup>
import { ref } from 'vue';

const numbers = ref([]);

for (let i = 1; i <= 250; i++) {
    numbers.value.push({
        value: i
    });
}

const numerosVendidos = ref([1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,23,24,25,27,28,30,31,34,36,38,40,41,43,44,46,48,50,51,53,55,57,59,61,67,69,72,76,78,80,83,85,86,90,93,96,99,100,101,112,115,121,126,128,139,141,154,171,200,201,216,220,244,248,249]);

function isSold(number) {
    return numerosVendidos.value.includes(number);
}
</script>

<template>
    <section class="title">
        <h1>Números de Rifa</h1>
        <div class="status-red">
            <h5>Vendidos:</h5>
            <div class="status-box red"></div>
        </div>
        <div class="status-white">
            <h5>Disponibles:</h5>
            <div class="status-box white"></div>
        </div>
        <div class="precio">
            <h5>Valor del número $1.000</h5>
        </div>
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
    <section class="info">
        <h4>Para comprar un número, por favor comunicarse</h4>
        <h4>con Claudia Ortiz al Número +56 9 3292 4555</h4>
        <p>Esta página es solo informativa.</p>
    </section>

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
.status-red{
    display: flex;
    justify-content: center;
    align-items: center;
}
.status-white{
    display: flex;
    justify-content: center;
    align-items: center;
}
.status-box{
    width: 25px;
    height: 25px;
    border: 1px solid black;
    margin-left: 20px;
}
.red{
    background-color: red;
}
.white{
    background-color: white;
}
.info{
    text-align: center;
}
</style>