<script>

export default {
    name: "CardVisualizer",
    props: {
        cards: Array,
        nStepVisualize: Number
    },
    data() {
        return {
            nCardsVisualized: this.nStepVisualize
        }
    },
    mounted() {
        console.log("Caricato il componente 'CardVisualizer'.");
    }
}
</script>

<template>
    <div class="text-center position-relative">
        <h2>CURRENT SERIES</h2>
        <div class="d-flex flex-wrap justify-content-center gap-3 pt-5">
            <!-- CARDS -->
            <div v-for="card in cards.slice(0, nCardsVisualized)">
                <div class="my-cardInfo d-flex align-items-center justify-content-center">
                    {{ card.type }} <br>
                    {{ card.price }}
                </div>
                <img :src="card.thumb" alt="comicThumb">
                <h3 class="h6 mt-3">{{ card.series }}</h3>
            </div>
        </div>
        <button v-show="nCardsVisualized < cards.length" @click="nCardsVisualized += nStepVisualize">LOAD MORE</button>
    </div>
</template>

<style scoped>
.my-cardInfo{
    position: absolute;
    opacity: 0;
    width: 200px;
    height: 200px;
    background-color: rgba(0, 0, 0, 0.8);
    transition: opacity .2s;
}
.my-cardInfo:hover{
    opacity: 1;
}

h3{
    max-width: 200px;
}
img{
    width: 200px;
    height: 200px;
    object-fit: cover;
    object-position: top;
}
h2{
    position: absolute;
    top: 0;
    left: 0;
    transform: translate(0, -50%);
    background-color: #0282f9;
    color: white;
    font-size: 1.5rem;
    padding: .5rem 2rem;
}
button{
    background-color: #0282f9;
    border: none;
    color: white;
    font-size: 1rem;
    padding: .5rem 4rem;
}
</style>
