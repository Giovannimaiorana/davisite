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
  { name: 'ROMANA', image: '/img/pizza1.svg' },
  { name: 'MARGHERITA', image: '/img/pizza2.svg' },
  { name: 'BELLA FRESCA', image: '/img/pizza3.svg' },
  { name: 'NORMA', image: '/img/pizza4.svg' },
  { name: 'TONNO', image: '/img/pizza5.svg' },
  { name: 'MORTAZZA', image: '/img/pizza6.svg' },
  { name: 'SALMONE', image: '/img/pizza7.svg' },
  { name: 'ORTOLANA', image: '/img/pizza8.svg' },
  { name: 'DAVI', image: '/img/pizza9.svg' },
  { name: 'MARINARA', image: '/img/pizza10.svg' },
  { name: 'DIAVOLA', image: '/img/pizza11.svg' },
  
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
  { name: 'LASAGNA', image: '/img/pasta1.svg' },
  { name: 'AMATRICIANA', image: '/img/pasta2.svg' },
  { name: 'CARBONARA', image: '/img/pasta3.svg' },
  { name: 'GNOCCHI ALLA SORRENTINA', image: '/img/pasta4.svg' },
  { name: 'TARTURFO & FUNGHI', image: '/img/pasta5.svg' },
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
      { opacity: 0, scale: 0.95, y: 30 },
      { opacity: 1, scale: 1, y: 0, duration: 0.6, ease: 'sine.out' }
    )
  }

  if (textEl) {
    gsap.fromTo(
      textEl,
      { opacity: 0, y: 15 },
      { opacity: 1, y: 0, duration: 0.5, ease: 'power3.out', delay: 0.1 }
    )
  }
})
// Anima il cambio di immagine con GSAP
watch([currentPizza, currentPasta, selectedCategory], async () => {
  await nextTick()

  const el = selectedCategory.value === 'pizza' ? pizzaImage.value : pastaImage.value
  if (!el) return

  gsap.fromTo(
    el,
    { opacity: 0, scale: 0, y: 20 },
    { opacity: 1, scale: 1, y: 0, duration: 0.8, ease: 'power3.out' }
  )
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
                    <img   ref="pizzaImage"  v-if="selectedCategory=== 'pizza'" class="pizza" :src="currentPizza.image"alt="">
                    <img   ref="pastaImage" v-if="selectedCategory=== 'pasta'" class="pizza" :src="currentPasta.image"alt="">
                    <p   ref="pizzaName" v-if="selectedCategory=== 'pizza'" class="nomePizza text-3xl lg:text-4xl xl:text-6xl ml-3 text-white font-dav sp"> {{ currentPizza.name }}</p>
                    <p    ref="pastaName"v-if="selectedCategory=== 'pasta'" class="nomePizza text-3xl lg:text-4xl xl:text-6xl ml-3 text-white font-dav sp"> {{ currentPasta.name }}</p>
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