<script lang="ts" setup>
import { gsap } from 'gsap'
interface Pizza {
  name: string
  image: string
}


interface Pasta {
  name: string
  image: string
}
const pizzas: Pizza[] = [
  { name: 'ROMANA', image: '/img/pizza1.webp' },
  { name: 'MARGHERITA', image: '/img/pizza2.webp' },
  { name: 'BELLA FRESCA', image: '/img/pizza3.webp' },
  { name: 'NORMA', image: '/img/pizza4.webp' },
  { name: 'TONNO', image: '/img/pizza5.webp' },
  { name: 'MORTAZZA', image: '/img/pizza6.webp' },
  { name: 'SALMONE', image: '/img/pizza7.webp' },
  { name: 'ORTOLANA', image: '/img/pizza8.webp' },
  { name: 'DAVI', image: '/img/pizza9.webp' },
  { name: 'MARINARA', image: '/img/pizza10.webp' },
  { name: 'DIAVOLA', image: '/img/pizza11.webp' },
  
]

const currentIndex = ref(0)

const currentPizza = computed(() => pizzas[currentIndex.value])
const totalPizzas = pizzas.length

function nextPizza() {
  currentIndex.value = (currentIndex.value + 1) % totalPizzas
}

function prevPizza() {
  currentIndex.value = (currentIndex.value - 1 + totalPizzas) % totalPizzas
}
//PASTA 
const pastas: Pasta[] = [
  { name: 'LASAGNA', image: '/img/pasta1.webp' },
  { name: 'AMATRICIANA', image: '/img/pasta2.webp' },
  { name: 'CARBONARA', image: '/img/pasta3.webp' },
  { name: 'GNOCCHI ALLA SORRENTINA', image: '/img/pasta4.webp' },
  { name: 'TARTURFO & FUNGHI', image: '/img/pasta5.webp' },
]
const currentIndexPasta = ref(0)

const currentPasta = computed(() => pastas[currentIndexPasta.value])
const totalPasta = pastas.length

function nextPasta() {
    currentIndexPasta.value = (currentIndexPasta.value + 1) % totalPasta
}

function prevPasta() {
    currentIndexPasta.value = (currentIndexPasta.value - 1 + totalPasta) % totalPasta
}
//categoria selezionata
const selectedCategory = ref<'pizza' | 'pasta'>('pizza');
console.log('categoria selezionata ',selectedCategory)
function selectCategory(category: 'pizza' | 'pasta') {
  selectedCategory.value = category;
}
//animazione
const pizzaImage = ref<HTMLElement | null>(null)
const pastaImage = ref<HTMLElement | null>(null)


const pizzaName = ref<HTMLElement | null>(null)
const pastaName = ref<HTMLElement | null>(null)
    watch([currentPizza, currentPasta, selectedCategory], async () => {
  await nextTick()

  const imageEl = selectedCategory.value === 'pizza' ? pizzaImage.value : pastaImage.value
  const textEl = selectedCategory.value === 'pizza' ? pizzaName.value : pastaName.value

  if (imageEl) {
    gsap.fromTo(
      imageEl,
      { opacity: 0, scale: 0, y: 20 },
      { opacity: 1, scale: 1, y: 0, duration: 0.6, ease: 'power3.out' }
    )
  }

  if (textEl) {
    gsap.fromTo(
      textEl,
      { opacity: 0, y: 10 },
      { opacity: 1, y: 0, duration: 0.5, ease: 'sine.out', delay: 0.1 }
    )
  }
})
onMounted(() => {
  pizzas.concat(pastas).forEach(item => {
    const img = new Image()
    img.src = item.image
  })
})
</script>

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
                    <button v-if="selectedCategory=== 'pizza'" @click="prevPizza" class="cursor-pointer">&lt;</button>
                    <button v-if="selectedCategory=== 'pasta'" @click="prevPasta" class="cursor-pointer">&lt;</button>
                    <p v-if="selectedCategory=== 'pizza'"  class="font-dav text-xl font-bold">{{ String(currentIndex + 1).padStart(2, '0') }}</p>
                    <p v-if="selectedCategory=== 'pasta'"  class="font-dav text-xl font-bold">{{ String(currentIndexPasta + 1).padStart(2, '0') }}</p>
                </div>
                <div class="containerLine">

                </div>
                <div class="containerNumber">
                    <p v-if="selectedCategory=== 'pizza'" class="font-dav text-xl font-bold">{{ String(totalPizzas).padStart(2, '0') }}</p>
                    <p v-if="selectedCategory=== 'pasta'" class="font-dav text-xl font-bold">{{ String(totalPasta).padStart(2, '0') }}</p>
                    <button v-if="selectedCategory=== 'pizza'" @click="nextPizza" class="cursor-pointer">&gt;</button>
                    <button v-if="selectedCategory=== 'pasta'" @click="nextPasta" class="cursor-pointer">&gt;</button>
                    
                </div> 
                <div class="flex gap-2 mt-2">

    
        </div>

            </div>
        </div>
        <div class="containerRight">
    
            <div class="containerRightLeft">
             
            </div>
            <div class="containerRightRight">
                <div v-if="selectedCategory==='pizza'" class="containerRightRightTop">
                    <p class="font-dav sp text-3xl lg:text-4xl xl:text-5xl font-bold text-right active cursor-pointer" @click="selectCategory('pizza')" >PIZZAS</p>
                    <p class="font-dav sp text-xl text-right cursor-pointer" @click="selectCategory('pasta')">PLATS DE PATES</p>
                    
                </div>
                <div v-if="selectedCategory==='pasta'" class="containerRightRightTop">
                    <p class="font-dav sp  text-3xl lg:text-4xl xl:text-5xl text-right cursor-pointer" @click="selectCategory('pasta')">PLATS DE PATES</p>
                    <p class="font-dav sp text-xl font-bold text-right active cursor-pointer" @click="selectCategory('pizza')" >PIZZAS</p>
                </div>
                <div class="containerRightRightBottom">
                    <img   ref="pizzaImage"  v-show="selectedCategory === 'pizza'" class="pizza" :src="currentPizza.image"alt="">
                    <img   ref="pastaImage" v-show="selectedCategory === 'pasta'" class="pizza" :src="currentPasta.image"alt="">
                    <p   ref="pizzaName" v-if="selectedCategory=== 'pizza'" class="nomePizza text-3xl lg:text-4xl xl:text-6xl ml-3 text-white font-dav sp"> {{ currentPizza.name }}</p>
                    <p    ref="pastaName"v-if="selectedCategory=== 'pasta'" class="nomePizza text-3xl lg:text-4xl xl:text-6xl ml-3 text-white font-dav sp"> {{ currentPasta.name }}</p>
                </div>
            </div>


        </div>
    </div>
    <!--container responsive-->

    <div class="containerResponsive">
        <div class="wrapperTitle">
            <p class="font-bold text-white font-dav text-2xl lg:text-4xl xl:text-5xl sp text-left">QUELQUES-UNS <br> DE NOS PLATS</p>
        </div>
        <div class="wrapperSelection">
            <div v-if="selectedCategory==='pizza'">
                    <p class="font-dav sp text-3xl lg:text-4xl xl:text-5xl font-bold text-right active cursor-pointer" @click="selectCategory('pizza')" >PIZZAS</p>
                    <p class="font-dav sp text-xl text-right cursor-pointer" @click="selectCategory('pasta')">PLATS DE PATES</p>
                </div>
            <div v-if="selectedCategory==='pasta'">
                    <p class="font-dav sp  text-3xl lg:text-4xl xl:text-5xl text-right cursor-pointer" @click="selectCategory('pasta')">PLATS DE PATES</p>
                    <p class="font-dav sp text-xl font-bold text-right active cursor-pointer" @click="selectCategory('pizza')" >PIZZAS</p>
                </div>
        </div>
        <div class="wrapperSection">
            <div class="containerNumber">
                <p v-if="selectedCategory=== 'pizza'"  class="font-dav text-4xl font-bold text-white">{{ String(currentIndex + 1).padStart(2, '0') }}</p>
                <p v-if="selectedCategory=== 'pasta'"  class="font-dav text-4xl font-bold text-white">{{ String(currentIndexPasta + 1).padStart(2, '0') }}</p>
            </div>
            <div class="arrowleft">
                <img  v-if="selectedCategory=== 'pizza'" @click="prevPizza"  class="cursor-pointer arrow" src="/img/arrowLeft.svg" alt="">
                <img  v-if="selectedCategory=== 'pasta'" @click="prevPasta"  class="cursor-pointer arrow" src="/img/arrowLeft.svg" alt="">
            </div>
            <div class="arrowRight">
                <img   v-if="selectedCategory=== 'pizza'" @click="nextPizza" class="cursor-pointer arrow" src="/img/arrowRight.svg" alt="">
                <img  v-if="selectedCategory=== 'pasta'" @click="nextPasta" class="cursor-pointer arrow" src="/img/arrowRight.svg" alt="">
            </div>
            <div class="nomePizzaMob">
                <p   ref="pizzaName" v-if="selectedCategory=== 'pizza'" class="nomePizza text-3xl lg:text-4xl xl:text-6xl ml-3 text-white font-dav sp text-right"> {{ currentPizza.name }}</p>
                <p    ref="pastaName"v-if="selectedCategory=== 'pasta'" class="nomePizza text-3xl lg:text-4xl xl:text-6xl ml-3 text-white font-dav sp text-right"> {{ currentPasta.name }}</p>
            </div>
       
      
            <div class="containerPizza">
                <img   ref="pizzaImage"  v-show="selectedCategory === 'pizza'" class="pizzamobile" :src="currentPizza.image"alt="">
                <img   ref="pastaImage" v-show="selectedCategory === 'pasta'" class="pizzamobile" :src="currentPasta.image"alt="">
            </div>
            

        </div>
        <div class="ordina">
            <p class="text-xs text-black font-dav spi">Commandez maintenant et dégustez-les chez vous !</p>
            <p v-if="selectedCategory=== 'pasta'" class=" text-3xl lg:text-4xl xl:text-6xl ml-3 text-black font-dav sp text-center cursor-pointer mt-3">COMMANDEZ </p>
        </div>

    </div>
</template>

<style scoped>
.containerResponsive{
    display: none;
}
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

    background-image: url(/img/davide.jpg);
    background-size: cover;
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
.containerNumber{
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
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
    .pizza{
    top: -120px;
    position: absolute;
    height: 280px;
}  
.wrapperPiatti{
    display: none;
}
.containerRightRight{
    width: 100%;
}
.containerResponsive{
    display: block;
    width: 100%;
    height: auto;
    background-color: black;
}
.wrapperTitle{
    width: 100%;
    height: auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 30px;

    background-color: black;
}
.wrapperSection{
    width: 100%;
    height: auto;
    background-color: #6F1D1B;
    display: flex;
    justify-content: center;
    position: relative;
    padding: 30px;
}
.containerMob{
    width: 100%;
    height: 100%;

}
.wrapperSelection{
    width: 100%;
    height: auto;
    background-color: #F5EBD9;
    padding: 30px;

}
.pizzamobile{
    width: 100%;
}
.containerPizza{
    margin: auto;
    width: 80%;
    height: 100%;
}
.containerNumber{
    width: 50px;
    height: 50px;
    position: absolute;
    top: 30px;
    right: 30px;
}
.arrowleft{
    position: absolute;
    left: 30px;
    top: 50%;
}
.arrowRight{
    position: absolute;
    right: 30px;
    top: 50%;
}
.nomePizzaMob{
    position: absolute;
    right: 30px;
    bottom: 10%;
    z-index: 40;
}
.arrow{
    height: 20px;
}
.ordina{
    width: 100%;
    height: auto;
    padding: 30px;
    background-color: #F5EBD9;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}
}


</style>