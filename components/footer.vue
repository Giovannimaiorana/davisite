<script lang="ts" setup>
const openPrivacyPolicy = () => {

  window.open('/documenti/maredilPP.pdf', '_blank');
};

</script>

<template>
    <div class="wrapperFooter">

            <div class="containerLogo">
           
            </div>

            <div class="containerInformation text-white ">
                <p class="font-bold text-xs text-center">Contrada la Torre 6 SUBIACO 00028 Rm</p>
                <p class="font-bold text-xs text-center">Mail: maredilcostruzioni17@gmail.com</p>
                <p class="font-bold text-xs text-center">Pec: maredilcostruzioni@legalmail.it</p>
                <p class="font-bold text-xs text-center">Tel +39 3278210185 </p>
                <p class="font-bold text-xs text-center">P.iva 15761541000</p>
                <p class="font-bold text-xs text-center">C.univ. M5UXCR1</p>
                <p class="font-bold  text-xs text-center underline cursor-pointer" @click="openPrivacyPolicy">Privacy Policy</p>
             
            </div>


    </div>
    
</template>

<style scoped>
.wrapperFooter{
    width: 100%;
    height: auto;
    background-color: black;
    display: flex;
    flex-direction: column;
    padding: 20px;
}
.containerLogo{
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}
.containerLogo img{
    height: 210px;
}
.containerSocial{
    display: flex;
    justify-content: center;
}
.containerSocial img{
    height: 90px;
}

.containerInformation{
    width: 100%;
    display: flex;
    margin-top: -40px;
    flex-direction: column;
    justify-content: center;
}

</style>