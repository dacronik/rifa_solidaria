<script setup>
import { onMounted, onUnmounted, ref } from "vue"


const particlesInstance = ref(null);

function initializeParticles() {
    particlesInstance.value = window.particlesJS('particle-background', {
        /* Configuración de partículas */
        "particles": {
            "number": {
                "value": 15,
                "density": {
                    "enable": true,
                    "value_area": 300
                }
            },
            "color": {
                "value": "#ffffff"
            },
            "shape": {
                "type": "circle",
                "stroke": {
                    "width": 0,
                    "color": "#000000"
                },
                "polygon": {
                    "nb_sides": 5
                },
            },
            "opacity": {
                "value": 0.8,
                "random": true,
                "anim": {
                    "enable": true,
                    "speed": 1,
                    "opacity_min": 0.1,
                    "sync": false
                }
            },
            "size": {
                "value": 5,
                "random": true,
                "anim": {
                    "enable": true,
                    "speed": 4,
                    "size_min": 0.3,
                    "sync": false
                }
            },
            "line_linked": {
                "enable": true,
                "distance": 150,
                "color": "#ffffff",
                "opacity": 0.4,
                "width": 1
            },
            "move": {
                "enable": true,
                "speed": 3,
                "direction": "none",
                "random": false,
                "straight": false,
                "out_mode": "bounce",
                "bounce": false,
                "attract": {
                    "enable": false,
                    "rotateX": 600,
                    "rotateY": 1200
                }
            }
        },
        "interactivity": {
            "detect_on": "canvas",
            "events": {
                "onhover": {
                    "enable": true,
                    "mode": "repulse"
                },
                "onclick": {
                    "enable": true,
                    "mode": "push"
                },
                "resize": true
            },
            // "modes": {
            //     "grab": {
            //         "distance": 800,
            //         "line_linked": {
            //             "opacity": 1
            //         }
            //     },
            //     "bubble": {
            //         "distance": 800,
            //         "size": 80,
            //         "duration": 2,
            //         "opacity": 0.8,
            //         "speed": 3
            //     },
            //     "repulse": {
            //         "distance": 400,
            //         "duration": 0.4
            //     },
            //     "push": {
            //         "particles_nb": 4
            //     },
            //     "remove": {
            //         "particles_nb": 2
            //     }
            // }
        },
        "retina_detect": true
    });
}

onMounted(() => {
    const script = document.createElement('script');
    script.src = 'https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js'
    script.onload = initializeParticles;
    document.head.appendChild(script);
})
onUnmounted(() => {
    if (particlesInstance.value) {
        particlesInstance.value.destroy();
    }
});
</script>

<template>
    <div id="particle-background"></div>
</template>

<style scoped>
#particle-background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
</style>