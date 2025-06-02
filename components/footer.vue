<script lang="ts" setup>
const openPrivacyPolicy = () => {

  window.open('/documenti/maredilPP.pdf', '_blank');
};

</script>

<template>
    <div class="wrapperFooter">
        <div class="containerLeft">
            <div>
                <img src="/img/daviCompressoBianco.svg" alt="">
            </div>
            <div class="mt-3 ml-4">
                <p class=" text-xs text-white text-left"> <span class="font-bold">ADRESSE :</span> Rue Dr César-Roux 9 1005 Lausanne(CH)<br><span class="font-bold">TELEPHONE :</span> <a href="tel:+0212176808">021 217 68 08</a><br> <span class="font-bold">EMAIL :</span> Info.impollonia@gmail.com</p>
                <p class=" text-xs text-white text-left"> Politique de confidentialite</p>
            </div>
            <div>

            </div>

        </div>
        <div class="containerRight">
            <div class="containerTitle">
                <p class=" text-sm text-white text- font-bold">HORARIRE D'OVERTURE</p>
            </div>
         
            <div class="containerOrario">
                <div class="left">
                    <p class=" text-xs text-white text-left font-bold mt-3">DIMANCHE </p>
                </div>
                <div class="right">
                    <p class=" text-xs text-white text-left font-light mt-3">18:00-22:00</p>
                </div>
               <!-- <div>
                    <p class=" text-xs text-white text-left font-bold mt-3">DIMANCHE <span class="ml-5 font-light">18:00-22:00</span></p>
                </div>
                <div>
                    <p class=" text-xs text-white text-left font-bold mt-3"> <span class="ml-5 font-light">11:00-13:15</span></p>
                </div>-->
            </div>
            <div class="containerOrario">
                <div class="left">
                    <p class=" text-xs text-white text-left font-bold mt-3">LUNDI </p>
                </div>
                <div class="right">
                    <p class=" text-xs text-white text-left font-light mt-3">11:00-13:15 <br> 18:00-22:00</p>
                </div>
            </div>
            <div class="containerOrario">
                <div class="left">
                    <p class=" text-xs text-white text-left font-bold mt-3">MARDI </p>
                </div>
                <div class="right">
                    <p class=" text-xs text-white text-left font-light mt-3">11:00-13:15 <br> 18:00-22:00</p>
                </div>
            </div>
            <div class="containerOrario">
                <div class="left">
                    <p class=" text-xs text-white text-left font-bold mt-3">MERCREDI </p>
                </div>
                <div class="right">
                    <p class=" text-xs text-white text-left font-light mt-3">11:00-13:15 <br> 18:00-22:00</p>
                </div>
            </div>
            <div class="containerOrario">
                
                <div class="left">
                    <p class=" text-xs text-white text-left font-bold mt-3">JEUDI </p>
                </div>
                <div class="right">
                    <p class=" text-xs text-white text-left font-light mt-3">11:00-13:15 <br> 18:00-22:00</p>
                </div>
            </div>
            <div class="containerOrario">
                <div class="left">
                    <p class=" text-xs text-white text-left font-bold mt-3">VENDREDI </p>
                </div>
                <div class="right">
                    <p class=" text-xs text-white text-left font-light mt-3">11:00-13:15 <br> 18:00-22:00</p>
                </div>
            </div>
            <div class="containerOrario">
                <div class="left">
                    <p class=" text-xs text-white text-left font-bold mt-3">SAMEDI </p>
                </div>
                <div class="right">
                    <p class=" text-xs text-white text-left font-light mt-3">18:00-22:00</p>
                </div>
            </div>


        </div>

    </div>
    
</template>

<style scoped>
.wrapperFooter{
    width: 100%;
    height: auto;
    background-color: black;
    display: flex;
    gap: 20px;
    padding: 30px;

}
.containerLeft{
    width: calc(100%/2);
    display: flex;
    flex-direction: column;
    justify-content: center;

display: flex;
flex-direction: column;
}
.containerLeft img{
    width: 200px;
}

.containerRight{
    width: calc(100%/2);
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    padding-top: 20px;
}
.containerOrario{
    width: 300px;
    display: flex;

}
.left{
width: 50%;

}
.right{
    width: 50%;

}
.containerTitle{
    width: 300px;
}
@media (max-width: 768px) {
    .wrapperFooter{
        display: flex;
        flex-direction: column;
    }
    .containerLeft{
        width: 100%;
        align-items: center;
    }
    .containerRight{
        width: 100%;
        align-items: center;
    }
    .left{
width: 50%;
display: flex;
justify-content:end; 
margin-right: 15px;

}
.right{
    width: 50%;

}
.containerTitle{
    display: flex;
    justify-content: center;
}
}
</style>