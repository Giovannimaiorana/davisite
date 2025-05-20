<script lang="ts" setup>
import footerComponent from '~/components/footer.vue';
import whoComponent from '~/components/whoComponent.vue';
import fastDeliveryComponent from '~/components/fastDeliveryComponent.vue';
import ourPizzeComponent from '~/components/ourPizzeComponent.vue';
import socialComponent from '~/components/socialComponent.vue';
import lottie from 'lottie-web';
const animationContainer = ref(null);
onMounted(() => {
  if (animationContainer.value) {
    lottie.loadAnimation({
      container: animationContainer.value,
      renderer: 'svg',
      loop: true,
      autoplay: true,
      path: '/img/scroll.json',
    });
  }
});

</script>

<template>
    <div class="wrapperHome">
        <div class="overlay"></div>
        <div class="containerText">
           <!-- <p class="font-mar  text-7xl md:text-9xl text-center text-white spac">DAVI'</p>-->
           <img class="imglogo" loading="lazy" src="/img/daviCompressoBianco.svg" alt="">
            <p class=" font-bold mottoStyle text-md md:text-xl text-white text-center font-dav">La vraie pizza italienne, chaque jour</p>
            <button class="buttonStyle font-dav sp"> COMMANDEZ</button>
            <div ref="animationContainer" class="animation mt-10"></div>
        </div>
    </div>
    <div class="containerWho">
        <ourPizzeComponent/>
    </div>
    <div class="containerWho">
        <socialComponent/>
    </div>
    <div class="containerWho">
        <whoComponent/>
    </div>
    <div class="containerWho">
        <fastDeliveryComponent/>
    </div>
    <div class="containerWho1">
        <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d5490.3113727432565!2d6.637876!3d46.524821!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x478c2f24b02637e1%3A0x35b3ec1c1f71dfb5!2sDavi%20Pizza%20%26%20Pasta!5e0!3m2!1sit!2sit!4v1746914677610!5m2!1sit!2sit" width="100%" height="450" style="border:0;"  loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>


    



</template>

<style scoped>
.wrapperHome{
    width: 100%;
    height: 100vh;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    background-image: url(/img/jumbotron6.jpg);
    background-size: cover;
    background-repeat: no-repeat;
}


.personalized2{
    color: rgb(89, 139, 192) ;
}
.overlay{
    position: absolute;
    width: 100%;
    height: 100vh;
    z-index: 7;
    background-color: rgba(0, 0, 0, 0.537);
}
.containerWho1{
    width: 100%;
}
.containerText{
    z-index: 10;
    display:flex ;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}
.mottoStyle{
    letter-spacing: 2px;
}
.d{
    background: linear-gradient(to bottom, rgba(44, 90, 153, 0.0) 0%,rgba(44, 90, 153, 0.0) 0%, rgba(44, 90,153, 1) 100%);
    background: linear-gradient(to bottom, rgba(0, 0, 0, 0.094) 40%,rgba(44, 90, 153, 0.0) 90%, rgba(44, 90,153, 1) 100%);
}
.spac{
    letter-spacing: 10px;
}
.sp{
    letter-spacing: 3px;
}
.animation{
    height: 90px;
}
.buttonStyle{
    border: 1px solid white;
    border-radius: 5px;
    padding: 8px 5px;
    color: white;
    margin-top: 20px;
}
.imglogo{
    height: 280px;
}
@media (max-width: 950px) {
    .imglogo{
    height: 250px;
}
}
@media (max-width: 768px) {
    .imglogo{
    height: 200px;
} 
}
@media (max-width: 420px) {
    .imglogo{
    height: 200px;
} 
}
</style>