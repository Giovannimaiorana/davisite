<script lang="ts" setup>
import footerComponent from '~/components/footer.vue';
</script>

<template>

    <div class="wrapperService">
        <div class="containerTitleMenu">
        
        </div>
        <div class="containerMenu">
            <p class=" text-2xl md:text-8xl font-bold text-white font-dav sp text-center">MENU A MIDI  </p>
        </div>
        <div class="menuWrapper">
            <div class="containerContent">
             
                <p class=" text-2xl md:text-6xl font-bold text-white font-dav sp text-left">   Menu Panuozzo </p>
                <p class="text-white text-sm md:text-md">Panuozzo préparé avec pâte à pizza, accompagné de frites et boisson.</p>

     
                <p class="mt-3 text-2xl md:text-23xl font-bold text-white font-dav sp text-right underline">12,90 CHF </p>
                <p class="text-white text-xs mt-3 "> <span class="text-sm font-bold">Important </span>Commande via l'application non disponible</p>

            </div>
            <div class="containerContent">
             
             <p class=" text-2xl md:text-6xl font-bold text-white font-dav sp text-left"> Pates du Jour </p>
             <p class="text-white text-sm md:text-md">Savourez nos plats de pâtes préparés chaque jour avec soin.
                Choisissez entre nos pâtes du jour (env. 100–120g) aux recettes variées,<br> ou laissez-vous tenter par nos lasagnes bolognaises maison, généreusement gratinées et pleines de goût.</p>

  
             <p class="text-md font-bold text-white font-dav sp text-right mt-3 "> <span>A emporter </span> <span class=" text-sm">9,90 CHF</span> </p>

             <p class=" text-md font-bold text-white font-dav sp text-right "> <span>Sur place </span> <span class=" text-sm">12 CHF</span> </p>
            </div>
            <div class="containerContent">
             
             <p class=" text-2xl md:text-6xl font-bold text-white font-dav sp text-left"> Parmigiana d'Aubergines Maison </p>
             <p class="text-white text-sm md:text-md">Un plat traditionnel aux saveurs authentiques : des tranches d’aubergines fondantes, une sauce tomate maison parfumée, de la mozzarella filante et du parmesan gratiné. <br> Un incontournable végétarien, préparé avec amour.</p>

  
             <p class="text-md font-bold text-white font-dav sp text-right mt-3 "> <span>A emporter </span> <span class=" text-sm">9,90 CHF</span> </p>

             <p class=" text-md font-bold text-white font-dav sp text-right "> <span>Sur place </span> <span class=" text-sm">12 CHF</span> </p>
            </div>
        </div>
        <div>
        <footerComponent/>
    </div>
    </div>



</template>

<style scoped>
.wrapperService{
    margin-top: 100px;
    width: 100%;
    height: 100vh;

    margin-top: 0px;
    background-color: #6F1D1B;

}
.sp{
    letter-spacing: 3px;
}
.containerTitleMenu{
    width: 100%;
    height: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
}
.containerMenu{
    width: 100%;
    height: 120px;
    padding: 30px;
    background-color: #F5EBD9;
    background-color: #6F1D1B;
}
.menuWrapper{
    width: 100%;
    height: auto;
    background-color: #F5EBD9;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-bottom:50px ;
}
.containerContent{
    width: 90%;
    height: auto;
    border-radius: 10px;
    background-color: #6f1c1bcb;
    margin-top: 50px;
    padding: 20px;
}
</style>