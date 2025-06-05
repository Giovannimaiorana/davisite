<script lang="ts" setup>

const route = useRoute()

// Funzione che controlla se la rotta è attiva
const isActive = (path: string) => route.path === path
</script>

<template>
    <div class="continerHeader">
        <div class="containerMenu">
            <a class="text-white cursor-pointer font-bold font-dav text-md sp " href="https://mylightspeed.app/JNAIKJWW/C-ordering"  target="_blank">MENU</a>
            <p class="text-white cursor-pointer font-bold font-dav text-md sp "><NuxtLink to="/menuamidi">NOS MENUS</NuxtLink></p>
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

    padding-bottom: 10px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.659);
}
.activeLanguage{
    color: #78f9ad;
}
.sp{
    letter-spacing: 5px;
}
</style>