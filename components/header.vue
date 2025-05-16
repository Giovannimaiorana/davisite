<script lang="ts" setup>
const route = useRoute()



const isActive = (path: string) => route.path === path
const emit = defineEmits(['toggleMenu'])


const onHamburgerClick = () => {
  emit('toggleMenu')
}
</script>

<template>
    <div class="continerHeader">
        <div class="containerLogo">
            <NuxtLink to="/">  <img src="/img/daviCompressoBianco.svg" alt=""></NuxtLink>
        </div>
        <div class="containerMenu">
            <p class="text-white cursor-pointer font-bold font-dav text-xs sp ">À PROPOS DE NOUS</p>
            <p class="text-white cursor-pointer font-bold font-dav text-xs sp "><NuxtLink to="/service">NOS SERVICES</NuxtLink></p>
            <p class="text-white cursor-pointer font-bold font-dav text-xs sp ">CONTACTEZ-NOUS</p>
        </div>
        <div class="containerResponsive">
            <img   @click="onHamburgerClick" class="cursor-pointer" src="/img/hamburgerMenu2.svg" alt="">
        </div>
    </div>
</template>

<style scoped>
.continerHeader {
    height: 100px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 30px;
    background-color: rgba(89, 139, 192, 0);
    z-index: 4;

}
.containerLogo{
    justify-content: space-between;
    display: flex;
}
.containerLogo img{
height: 80px;
}
.activeLanguage{
    color: #78f9ad;
}
.containerMenu{
    display: flex;
    align-items: center;
    gap: 20px;
}
.containerMenu p:hover{
    color: red;
    color: #F5EBD9;
}
.containerResponsive{
    display: none;
}
.sp{
    letter-spacing: 3px;
}
@media (max-width: 768px) {
    .continerHeader{
        padding: 10px;
    }
    .containerMenu{
        display: none;
    }
    .containerResponsive{
    display: flex;
    }
    .containerResponsive img{
        height: 30px;
    }
    .containerLogo img{
height: 60px;
}

}
</style>