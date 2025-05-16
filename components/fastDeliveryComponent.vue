<script lang="ts" setup></script>

<template>
  <div class="bg-[#F5EBD9] py-10 px-6">
    <div class="flex flex-col md:flex-row gap-8 justify-between items-center max-w-6xl mx-auto color1">
      <div class="flex flex-col items-center text-center max-w-xs">
        <img src="/img/icon1.jpg" alt="icon1" class="h-32 w-auto mb-4" />
        <p class="font-dav text-xl font-bold tracking-wider">INGREDIENTS DE QUALITE</p>
        <p class="font-dav text-xs mt-2">Nous selectionnons uniquement des produits frais et authentiques, sans compromis.</p>
      </div>
      
      <div class="flex flex-col items-center text-center max-w-xs color2">
        <img src="/img/icon2.jpg" alt="icon2" class="h-32 w-auto mb-4" />
        <p class="font-dav text-xl font-bold tracking-wider">SERVICE DE LIVRAISON RAPIDE</p>
        <p class="font-dav text-xs mt-2">Vos plats preferes, livres chauds et a temps, directement chez vous.</p>
      </div>
      
      <div class="flex flex-col items-center text-center max-w-xs color3">
        <img src="/img/icon3.jpg" alt="icon3" class="h-32 w-auto mb-4" />
        <p class="font-dav text-xl font-bold tracking-wider"> ACCUEIL CHALEUREUX ET SINCERE</p>
        <p class="font-dav text-xs mt-2">Chez nous, chaque client est accueilli comme un ami, avec le sourire.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.wrapperFast{
    width: 100%;
    height: 300px;
    padding: 30px;
    display: flex;
    background-color: #F5EBD9;
}
.containersection{
    width: calc(100% / 3);
    height: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}
.containersection img{
    height: 150px;
}
.sp{
    letter-spacing: 5px;
}
.sp{
    letter-spacing: 3px;
}
</style>