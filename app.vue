<script lang="ts" setup>
import headerComponent from './components/header.vue';
import headerSidebar from './components/headerSidebar.vue';
import footerComponent from './components/footer.vue';

useSeoMeta({
  title: 'Davì Pizza & Pasta - Il Gusto Autentico Italiano',
  ogTitle: 'Davì Pizza & Pasta - Gusto e Tradizione Italiana',
  description: 'Scopri il sapore autentico della vera pizza italiana da Davì Pizza & Pasta. Ingredienti freschi, impasti artigianali e passione per la cucina tradizionale.',
  ogDescription: 'Da Davì Pizza & Pasta assapori pizze cotte a legna, pasta fresca e specialità italiane preparate con ingredienti selezionati. Vieni a trovarci o ordina online!',
  ogImage: 'https://xn--davpizzaepasta-nlb.ch/img/daviCompressoBianco.svg', 
  ogSiteName: 'Davì Pizza & Pasta',
  ogUrl: 'https://xn--davpizzaepasta-nlb.ch/',
})
useHead({
  link: [
    { rel: 'icon', type: 'image/x-icon', href: '/img/faviconMaredil.svg' }
  ]
})

const isMenuOpen = ref(false)
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
const route = useRoute()
watch(route, () => {
  isMenuOpen.value = false
})

// ✅ Variabile per colore header
const scrolledPastHero = ref(false)

const handleScroll = () => {
  const scrollY = window.scrollY;
  const viewportHeight = window.innerHeight;
  const thresholdMobile = viewportHeight * 0.1; // 30% di 100vh per dispositivi mobili
  const thresholdDesktop = viewportHeight * 0.1; // 100vh per dispositivi desktop
  
  // Controlla la larghezza della finestra
  const isMobile = window.innerWidth < 768;

  // Cambia il colore dell'header per dispositivi mobili (30% di 100vh)
  if (isMobile) {
    scrolledPastHero.value = scrollY > thresholdMobile;
  } else {
    // Cambia il colore dell'header per desktop (dopo aver scrollato oltre 100vh)
    scrolledPastHero.value = scrollY > thresholdDesktop;
  }
}

const handleResize = () => {
  if (window.innerWidth > 768) {
    isMenuOpen.value = false;
    scrolledPastHero.value = false; // Reset per gli schermi grandi
  }
}

onMounted(() => {
  window.addEventListener('resize', handleResize);
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('resize', handleResize);
  window.removeEventListener('scroll', handleScroll);
});
</script>



<template>
  <nav class="sticky-header" :class="{ 'scrolled-red': scrolledPastHero || isMenuOpen }" >
    <headerComponent @toggleMenu="toggleMenu" />
  </nav>
  <main class="mainStyle" >
      <headerSidebar class="responsiveSidebar" v-if="isMenuOpen"/>
        <NuxtPage />

  </main>

  
</template>

<style scoped>
.sticky-header {
  position: fixed;
  width: 100%;
  top: -5px;
  right: 0;
  z-index: 30;
  background-color: transparent;
  transition: background-color 0.4s ease, transform 0.4s ease;
}

/* ✅ Applica stile e animazione quando scrolled */
.scrolled-red {
  background-color: rgb(189, 0, 0);
  background-color: #6F1D1B;
  transform: translateY(4px); /* effetto discesa leggera */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2); /* ombra elegante */
}
.mainStyle{
  position: relative;
}
.wrapperHome{
  width: 100%;
  height: 100vh;
}
.wrapperService{
  width: 100%;
  height: 300px;

}
.wrapperHowis{
  width: 100%;
  height: auto;
  background-color: black;
}

@media (max-width: 768px) {
  .responsiveSidebar{
    width: 100%;
    height: 100%;
    position: fixed;
    top: 96px;
    left: 0;
    bottom: 0;
    z-index: 1000;
  }
}
</style>