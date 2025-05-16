<script lang="ts" setup>
import { ref, onMounted } from 'vue';
import lottie from 'lottie-web';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';

// Registriamo il plugin ScrollTrigger di GSAP
gsap.registerPlugin(ScrollTrigger);

const animationContainer = ref(null);
onMounted(() => {
  if (animationContainer.value) {
    // Carica l'animazione Lottie con autoplay disabilitato
    const animation = lottie.loadAnimation({
      container: animationContainer.value,
      renderer: 'svg',
      loop: false,
      autoplay: false, // Impostiamo autoplay su false
      path: '/img/instagramAnimation.json',
    });
    

    

    // Imposta la velocità dell'animazione più lenta (esempio: 0.5 significa metà della velocità normale)
    animation.setSpeed(0.9);

    // Usa GSAP per aggiungere un ritardo prima di far partire l'animazione
    gsap.from(animationContainer.value, {
      opacity: 0,
      duration: 1,
      delay: 1, // Ritardo di 1 secondo prima di far partire l'animazione
      scrollTrigger: {
        trigger: animationContainer.value,
        start: 'top 95%', // Quando l'elemento è al 90% della viewport
        end: 'bottom top',
        onEnter: () => {
          // Aggiungi un ritardo prima di far partire l'animazione
          setTimeout(() => {
            animation.play(); // Avvia l'animazione con ritardo
          }, 900); // Ritardo di 1 secondo
        },
        onLeave: () => {
          animation.stop(); // Ferma l'animazione quando esce dalla viewport
        },
        markers: false, // Puoi mettere true per visualizzare i marker di debug
      },
    });
  }
});


const goToInstagram = () => {
  window.open('https://www.instagram.com/davi_pizza_pasta?igsh=b3phMjdzeHU1aGtp', '_blank');
};


</script>

<template>
    <div class="wrapperSocial">
        <div class="containerLeft">
            <p class="font-dav text-white text-4xl sm:text-4xl md:text-5xl lg:text-4xl xl:text-5xl font-bold text-center md:text-right  "> UIVEZ-NOUS SUR <br> INSTAGRAM</p>
            <p class="font-dav text-white text-xs text-center">cliquer <span class="arroww">-------</span></p>
        </div>
        <div class="containerRight">
            <div ref="animationContainer" @click="goToInstagram" class="animation cursor-pointer"></div>
        </div>

    </div>
</template>

<style scoped>
.wrapperSocial{
    width: 100%;
    height: 400px;
    background-color: black;
    display: flex;
    padding: 40px;
    gap: 30px;
}
.containerLeft{
    width: 50%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: end;
    justify-content: center;
}
.containerRight{
    width: 50%;
    height: 100%;
    display: flex;
    justify-content: flex-start;
    align-items: center;
}
.animation{
    height: 100%;
}
.arroww{
    letter-spacing: -1px;
}
@media (max-width: 768px) {
.wrapperSocial{
    flex-direction: column;
    height: auto;
}
.containerLeft{
    width: 100%;
    justify-content: center;
    align-items: center;

}
.containerRight{
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}
.animation{
    width: 60%;
}
}
</style>
