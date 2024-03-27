<script setup>
import CardComp from './CardComp.vue'
import NumbersComp from './NumbersComp.vue'
import FooterComp from './FooterComp.vue'
</script>

<template>
    <section class="background">
        <v-container>
            <article class="title">
                <h1>Gran Rifa a Beneficio</h1>
                <h6>Para Rodrigo Ortiz</h6>
            </article>
            <article class="list-premios">
                <CardComp />
            </article>
            <article class="numeros-rifa">
                <NumbersComp/>
            </article>
        </v-container>
        <FooterComp/>
    </section>
</template>

<style scoped>
.background {
    display: grid;
}

.title {
    font-size: 3rem;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    font-family: "Monoton";
    font-size: 400;
    color: aliceblue;
}

.title h1{
    background: #2193b0;
    /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #6dd5ed, #2193b0);
    background: linear-gradient(to right, #6dd5ed, #2193b0);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;

}
</style>