<script setup>
//const transparent = "rgba(255, 255, 255, 0)";


const productos = [
  {
    nombre: "bueyes",
    img: "img/bueyes.jpeg"
  },
  {
    nombre: "espejo-sol",
    img: "img/espejo-sol.jpeg"
  },
  {
    nombre: "Espejo Mosaico",
    img: "img/espejo.jpeg"
  },
  {
    nombre: "Pisco",
    img: "img/pisco.jpeg"
  },
  {
    nombre: "Perro Adorno",
    img: "img/perro.jpeg"
  },
  {
    nombre: "Tabla para Picar",
    img: "img/patita.jpeg"
  },
  {
    nombre: "servilletero",
    img: "img/servilletero.jpeg"
  },
  {
    nombre: "Llavero",
    img: "img/llavero.jpeg"
  },
  {
    nombre: "Poleras",
    img: "img/polera.webp"
  },
  {
    nombre: "Marqueza",
    img: "img/marqueza.png"
  },
  {
    nombre: "Hielera",
    img: "img/hielera.jpeg"
  },
  {
    nombre: "Pie de Limon",
    img: "img/pie-limon.jpeg"
  }
]
</script>

<template>
  <v-card class="mb-4 bg-lime-lighten-2" prepend-icon="mdi-gift-open">
    <template v-slot:title>
      Premios
    </template>
  </v-card>
  <v-row align="center" justify="center">
    <template v-for="producto in productos" :key="producto.nombre">
      <v-col cols="12" md="3">
        <v-hover v-slot="{ isHovering, props }">
          <v-card class="border" elevation="0" rounded="2" :class="{ 'on-hover': isHovering }" v-bind="props" >
            <v-img :src="producto.img" :aspect-ratio="1" cover>
              <v-expand-transition>
                <div v-if="isHovering"
                  class=" transition-fast-in-fast-out bg-lime-lighten-2 v-card--reveal text-h4 transparent"
                  :class="{ isHovering }" style="height: 100%;">
                  <v-card-text class=" text-center text-h4 pb-2">{{ producto.nombre }}</v-card-text>
                </div>
              </v-expand-transition>
              <template v-slot:placeholder>
                <v-row align="center" class="fill-height ma-4" justify="center">
                  <v-progress-circular color="grey-lighten-5" indeterminate></v-progress-circular>
                </v-row>
              </template>
            </v-img>
          </v-card>
        </v-hover>
      </v-col>
    </template>
  </v-row>
</template>

<style scoped>
.transparent {
    transition: opacity 0.3s ease-in-out;
}

.transparent:not(.on-hover) {
    opacity: 0.75;
}


.v-card--reveal {
  display: flex;
  align-items: center;
  bottom: 0;
  justify-content: center;
  position: absolute;
  width: 100%;
}
/* .font-details{
  color: #2a3531;
  font-family: 'Ubuntu', 'Roboto';
  font-size: 2rem;
} */
</style>