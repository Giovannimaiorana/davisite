<script lang="ts" setup></script>

<template>
    <div class="wrapperContainerWHo">
      <!--  <div class="contaierTitle">
            <p class="text-white font-dav sp text-4xl text-center font-bold">A PROPOS DE NOUS</p>
        </div>-->
        <div class="containerContent">
            <div class="containerLeft">
                <p class=" font-dav sp text-5xl text-center md:text-right font-bold ">A PROPOS <br> DE NOUS</p>
                <p class=" font-dav text-md line text-center md:text-right mt-4">Nous sommes deux frères originaires de Messine, élevés les mains dans la pâte et le cœur dans la cuisine familiale. De Messine à la Suisse, nous avons emporté avec nous le parfum du four allumé, la passion de la pizza et l’amour des pâtes faites comme autrefois. C’est ainsi qu’est née Davì : bien plus qu’une simple pizzeria, un coin de Sicile où chaque plat raconte une histoire faite de tradition, d’ingrédients authentiques et d’un accueil chaleureux. Qu’il s’agisse d’une pizza croustillante ou d’un plat de pâtes au goût sincère, chaque bouchée vous emmène en voyage dans notre terre natale. Nous avons uni notre expérience, nos racines et l’esprit de famille pour créer un lieu où l’on se sent vraiment chez soi.Bienvenue chez Davì – notre histoire, notre cuisine, notre Sicile.</p>
                
            </div>
            <div class="containerRight">
               
            </div>

        </div>

    </div>
</template>

<style scoped>
.wrapperContainerWHo{
    width: 100%;
    height: 600px;
    flex-direction: column;
}
.contaierTitle{
    width: 100%;
    height: auto;
}
.containerContent{
    width: 100%;
    display: flex;
    gap: 30px;
}
.containerLeft{
    width: 50%;
    height: 600px;
    padding: 30px;
    overflow-y: scroll;
    color: white;
}
.containerRight{
    width: 50%;
    height: 600px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-image: url(/img/chisiamo.jpg);
    background-repeat: no-repeat;
    background-size: cover;
}

.sp{
    letter-spacing: 5px;
}
.line{
    line-height: 35px;
}
/***button  */
/* From Uiverse.io by TISEPSE */ 

@media (max-width: 768px) {
    .wrapperContainerWHo{
    width: 100%;
    height: auto;
    flex-direction: column;
}
    .containerContent{
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
}  
.containerLeft{
    width: 100%;
    height: 100%;
    background-image: none;
background-color: #F5EBD9;
color: black;

}
.containerRight{
display: none;
}
}
</style>