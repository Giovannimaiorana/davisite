<script lang="ts" setup></script>

<template> 
    <div class="wrapperPiatti telephone">
        <div class="containerLeft">
            <div class="containerTop">
                <p class="font-bold text-white font-dav text-3xl lg:text-4xl xl:text-5xl sp text-right">QUELQUES-UNS <br> DE NOS PLATS</p>
                <p class="text-xs text-white font-dav spi">Commandez maintenant et dégustez-les chez vous !</p>
                <div class="containerButton">
                    <button class="buttonStyle font-dav sp"> COMMANDEZ</button>
                </div>

            </div>
            <div class="containerBottom">
                <div class="containerNumber">
                    <p class="font-dav text-xl font-bold">01</p>
                </div>
                <div class="containerLine">

                </div>
                <div class="containerNumber">
                    <p class="font-dav text-xl font-bold">09</p>
                </div> 

            </div>
        </div>
        <div class="containerRight">
    
            <div class="containerRightLeft">
             
            </div>
            <div class="containerRightRight">
                <div class="containerRightRightTop">
                    <p class="font-dav sp text-3xl lg:text-4xl xl:text-5xl font-bold text-right active">PIZZAS</p>
                    <p class="font-dav sp text-xl text-right">PLATS DE PATES</p>
                    <p class="font-dav sp text-xl text-right">DESSERTS</p>

                </div>
                <div class="containerRightRightBottom">
                    <img class="pizza" src="/img/pizza1.svg" alt="">
                    <p class="nomePizza text-3xl lg:text-4xl xl:text-6xl ml-3 text-white font-dav sp">MARGHERITA</p>
                </div>
            </div>


        </div>
    </div>
</template>

<style scoped>
.wrapperPiatti{
    width: 100%;
    height: 700px;
    display: flex;
}
/**PARTE SINISTRA */
.containerLeft{
    width: 30%;
    height: 100%;
    display: flex;
    flex-direction: column;
}
.containerTop{
    width: 100%;
    height: 80%;
    padding:30px;
    display: flex;
    flex-direction: column;
    align-items: end;
    justify-content: center;
    background-color: #6F1D1B;
}
.containerBottom{
    width: 100%;
    height: 20%;
    background-color: #6F1D1B;
    background-color: white;
    background-color: #F5EBD9;
    display: flex;
    align-items: center;
    padding: 30px;
    gap: 20px;
    justify-content: center;

}
.containerButton{
    width: 100%;
    display: flex;
    justify-content: end;
    margin-top: 50px;

}
.containerLine{
    width: 200px;
    border: 2px solid black;
}
/**PARTE DESTRA */

.containerRight{
    width: 70%;
    height: 100%;
    display: flex;
    position: relative;

}
.containerRightLeft{
    width: 50%;
    height: 100%;

    background-image: url(/img/backpiatti.jpg);
}
.containerRightRight{
    width: 50%;
    height: 100%;

    display: flex;
    flex-direction: column;
}
.containerRightRightTop{
    width: 100%;
    height: 50%;
    background-color: #F5EBD9;
    padding: 30px;
    
}
.containerRightRightBottom{
    width: 100%;
    height: 50%;
    background-color: #6F1D1B;
    position: relative;
    display: flex;
    align-items: end;

}
.pizza{
    top: -150px;
    position: absolute;
    height: 390px;
}

/**CONTENUTI */
.sp{
    letter-spacing: 3px;
}
.spi{
    letter-spacing: 1px;
}
.buttonStyle{
    border: 1px solid white;
    border-radius: 5px;
    padding: 8px 5px;
    color: white;
}
@media (max-width: 1124px) {
    .containerRightLeft{
    width: 40%;
}
.containerRightRight{
    width: 60%;
}
.pizza{
    top: -140px;
    position: absolute;
    height: 330px;
}
}


@media (max-width: 960px) {
    .pizza{
    top: -120px;
    position: absolute;
    height: 300px;
}  
}
@media (max-width: 850px) {
    .telephone{
        display: none;
    }
    .pizza{
    top: -120px;
    position: absolute;
    height: 280px;
}  
.containerRightLeft{
    display: none;
}
.containerRightRight{
    width: 100%;
}
}


</style>