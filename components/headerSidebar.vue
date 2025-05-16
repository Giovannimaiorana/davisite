<script lang="ts" setup>

const route = useRoute()

// Funzione che controlla se la rotta è attiva
const isActive = (path: string) => route.path === path
</script>

<template>
    <div class="continerHeader">
        <div class="containerMenu">
            <p :class="[isActive('/service') ? 'active' : 'text-white', 'fext-white cursor-pointer font-bold font-dav sp']"><NuxtLink to="/service">SERVIZI</NuxtLink></p>
            <p class="text-white cursor-pointer font-bold font-dav sp">CHI SIAMO</p>
            <p class="text-white cursor-pointer font-bold font-dav sp">CONTATTI</p>
        </div>

    </div>
</template>
<style scoped>
.continerHeader{
    background-color: #6F1D1B;
    padding: 20px;
}
.active{
    color: rgb(44, 90, 153); 
}
.containerMenu{
    display: flex;
    flex-direction: column;
    gap: 20px;
}
.containerMenu p:hover{
    color: rgb(44, 90, 153);
}
.containerMenu p{
    border-bottom: 1px solid white;
    padding-bottom: 10px;

}
.activeLanguage{
    color: #78f9ad;
}
.sp{
    letter-spacing: 5px;
}
</style>