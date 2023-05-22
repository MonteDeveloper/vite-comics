<script>

export default {
    name: "StaticJumbo",
    props: {
        jumboImg: String
    },
    mounted() {
        console.log("Caricato il componente 'StaticJumbo'.");
    }
}
</script>

<template>
    <div class="my-jumbo" :style="{ backgroundImage: `url(${jumboImg})` }"></div>
</template>

<style scoped>
.my-jumbo{
    height: 400px;
    width: 100%;
    background-size: cover;
}
</style>
