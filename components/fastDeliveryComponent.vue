<script lang="ts" setup></script>

<!--<template>
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
</template>-->
<template>
  <div class="wrappercomponent">
    <div class="fascia">
      <p class="text-white text-center text-6xl">NOUS..</p>
    </div>
    <div class="containerMaterie">
      <div class="blocco1">
        <div class="containerLeft">

        </div>
        <div class="containerRight">
          <p class=" font-bold text-2xl md:text-5xl font-bold text-black font-dav sp">INGREDIENTS DE <br>QUALITE</p>
          <p class="font-dav text-xs mt-2 text-black sp">Nous selectionnons uniquement des produits frais, authentiques et de saison, rigoureusement choisis pour leur gout et leur origine. <br> Aucun compromis n’est fait sur la qualite <br> chaque ingredient reflete notre engagement envers l’excellence et la tradition culinaire.</p>
          <button class="buttonStyledark font-dav sp"> MENU</button>
        </div> 
      </div>
      <div class="bloccoTransparent">
        <div>
          <p class=" text-2xl md:text-8xl font-bold text-white font-dav sp text-center">DECOUVREZ NOTRE MENU</p>
        </div>

        <button class="buttonStyle font-dav sp"> MENU </button>
      </div>
      <div class="blocco1">

</div>   


    </div>


    <div class="containerMaterie2">

    </div>

  </div>
</template>
<style scoped>
.wrappercomponent {
  width: 100%;
  height: auto;
  background-color: black;

}
.fascia{
  width: 100%;
  height: 200px;
  background-color: black;
  display: flex;
  align-items: center;
  justify-content: center;
}
.containerMaterie{
  width: 100%;

  height:100%;
  background-color: black;

  background-image: url(/img/impasto.webp);
  background-size: cover;
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;

}
.containerMaterie2{
  width: 100%;


  height: 200vh;
  background-color: black;
  background-image: url(/img/bonappeti.webp);
  background-size: cover;
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;

}
.blocco1{
  width: 100%;
  height: 500px;
  background-color: #F5EBD9;
  display: flex;
}
.bloccoTransparent{
  width: 100%;
  height: 600px;
  background-color: rgba(0, 0, 0, 0.2);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.sp {
  letter-spacing: 5px;
}
.buttonStyle{
    border: 1px solid white;
    border-radius: 5px;
    padding: 8px 8px;
    color: white;
    margin-top: 20px;
}
.containerLeft{
  width: 50%;
  height: 100%;
  background-image: url(/img/quality.webp);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
.containerRight{
  width: 50%;
  height: 100%;
  padding: 30px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.buttonStyledark{
  width: 200px;
  border: 1px solid black;
    border-radius: 5px;
    padding: 8px 5px;
    color: black;
    margin-top: 20px;
}
.sp {
  letter-spacing: 3px;
}
@media (max-width: 850px) {
  .containerLeft{
  width: 30%;
  height: 100%;
  background-image: url(/img/quality.webp);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
.containerRight{
  width: 70%;
  height: 100%;
  padding: 30px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
}
@media (max-width: 460px) {
  .containerLeft{
  width: 10%;
  height: 100%;
  background-image: url(/img/quality.webp);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
.containerRight{
  width: 80%;
  height: 100%;
  padding: 30px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.containerMaterie{
  width: 100%;

  height:100%;
  background-color: black;

  background-image: url(/img/impasto.webp);
  background-size: cover;
  background-attachment:scroll;
  background-position: center;
  background-repeat: no-repeat;

}
.containerMaterie2{
  width: 100%;


  height: 200vh;
  background-color: black;
  background-image: url(/img/bonappeti.webp);
  background-size: cover;
  background-attachment: scroll;
  background-position: initial;
  background-repeat: no-repeat;

}
}
</style>