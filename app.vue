<script lang="ts" setup>
import headerComponent from './components/header.vue';
import headerSidebar from './components/headerSidebar.vue';
import footerComponent from './components/footer.vue';

useSeoMeta({
  title: 'Davì Pizza & Pasta - Le Goût Authentique Italien',
  ogTitle: 'Davì Pizza & Pasta - Goût et Tradition Italienne',
  description: 'Découvrez la saveur authentique de la vraie cuisine italienne chez Davì Pizza & Pasta. Ingrédients frais, pâtes artisanales et passion pour la cuisine traditionnelle.',
  ogDescription: 'Chez Davì Pizza & Pasta, dégustez des pizzas, des pâtes fraîches et des spécialités italiennes préparées avec des ingrédients sélectionnés. Venez nous rendre visite ou commandez en ligne !',
  ogImage: 'https://www.davìpizzaepasta.ch/img/favicon.png', 
  ogSiteName: 'Davì Pizza & Pasta',
  ogUrl: 'https://www.davìpizzaepasta.ch/',
})


useHead({
  meta: [
    { property: 'og:title', content: 'Davì Pizza & Pasta - Le Goût Authentique Italien' },
    { property: 'og:description', content: 'Découvrez la saveur authentique de la vraie cuisine italienne chez Davì Pizza & Pasta. Ingrédients frais, pâtes artisanales et passion pour la cuisine traditionnelle.' },
    { property: 'og:image', content: 'https://www.davìpizzaepasta.ch/img/favicon.png' },
    { property: 'og:url', content: 'https://www.davìpizzaepasta.ch/' },
    { property: 'og:site_name', content: 'Davì Pizza & Pasta' },
    { property: 'og:type', content: 'website' }
  ],
  link: [
    { rel: 'icon', type: 'image/x-icon', href: '/img/favicon.png' }
  ],
  script: [
    {
      type: 'application/ld+json',
      children: JSON.stringify({
        '@context': 'https://schema.org',
        '@type': 'Restaurant',
        'name': "Davì Pizza & Pasta",
        "image": "https://www.davìpizzaepasta.ch/img/favicon.png",
        "address": {
          "@type": "PostalAddress",
          "streetAddress": "Rue Dr César-Roux 9",
          "addressLocality": "Lausanne",
          "postalCode": "1005",
          "addressCountry": "CH"
        },
        'telephone': '0212176808',
        'url': "https://xn--davpizzaepasta-nlb.ch/",
        "servesCuisine": ["Italian", "Pizza", "Pasta"],
        'sameAs': [
          'https://www.instagram.com/davi_pizza_pasta?igsh=b3phMjdzeHU1aGtp'
        ],
        "openingHours": [
          "Mo 11:00-13:15",
          "Mo 18:00-22:00",
          "Tu 11:00-13:15",
          "Tu 18:00-22:00",
          "We 11:00-13:15",
          "We 18:00-22:00",
          "Th 11:00-13:15",
          "Th 18:00-22:00",
          "Fr 11:00-13:15",
          "Fr 18:00-22:00",
          "Sa 18:00-22:00",
          "Su 18:00-22:00"
        ],
        'description': 'Découvrez la saveur authentique de la vraie cuisine italienne chez Davì Pizza & Pasta.'
      }) as any
    } as any
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