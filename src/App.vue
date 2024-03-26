<template>
  <v-app>
    <v-main id="app">
      <particle-background />
      <router-view />
    </v-main>
  </v-app>
</template>

<script setup>
import ParticleBackground from "@/components/ParticleBackground.vue"

</script>

<style>
#app {
  font-family: 'Ubuntu', sans-serif, 'Roboto';
  background: #0F2027;
  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #2C5364, #203A43, #0F2027);
  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #2C5364, #203A43, #0F2027);
  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

}
</style>
