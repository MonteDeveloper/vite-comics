<script>

export default {
    name: "InfolistBar",
    props: {
        infolist: Array
    },
    data() {
        return {
            activeNavEl: 0
        }
    },
    mounted() {
        console.log("Caricato il componente 'InfolistBar'.");
    }
}
</script>

<template>
    <div class="d-flex justify-content-between">
        <div class="d-flex gap-3 align-items-center" v-for="infoElement in infolist">
            <img :src="'./src/assets/img/' + infoElement.imgFile" alt="LOGO">
            <h2>{{ infoElement.name }}</h2>
        </div>
    </div>
</template>

<style scoped>
div {
    color: white;
    height: 200px;
}

h2{
    font-size: 1rem;
}

img{
    height: 50px;
}
</style>
