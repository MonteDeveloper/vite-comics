<script>

export default {
    name: "LogoNavbar",
    props: {
        logoPath: String,
        navElements: Array
    },
    data() {
        return {
            activeNavEl: 0
        }
    },
    mounted() {
        console.log("Caricato il componente 'LogoNavbar'.");
    }
}
</script>

<template>
    <div class="d-flex justify-content-between align-items-center">
        <img :src="logoPath" alt="LOGO">
        <ul class="d-flex gap-4 p-0 m-0">
            <li class="d-flex align-items-center" :class="index == activeNavEl ? 'activeNavEl' : ''" v-for="(li, index) in navElements" @click="activeNavEl = index">
                {{ li.trim() }}
            </li>
        </ul>
    </div>
</template>

<style scoped>
img{
    height: 100px;
}

li{
    list-style: none;
    height: 130px;
    font-weight: 500;
    transition: color .2s;
}

li:hover{
    color: #0282f9;
    cursor: pointer;
}

.activeNavEl{
    color: #0282f9;
    border-bottom: 4px solid #0282f9;
}
</style>
