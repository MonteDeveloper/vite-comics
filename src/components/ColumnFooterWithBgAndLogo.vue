<script>

export default {
    name: "ColumnFooterWithBgAndLogo",
    props: {
        bgImg: String,
        logoImg: String,
        columns: Array
    },
    mounted() {
        console.log("Caricato il componente 'ColumnFooterWithBgAndLogo'.");
    }
}
</script>

<template>
    <div class="my-topBox py-4" :style="{ backgroundImage: `url(${bgImg})` }">
        <div class="container text-white d-flex justify-content-between">
            <div class="d-flex flex-wrap gap-5 align-items-start">
                <div v-for="column in columns">
                    <div v-if="!(column instanceof Array)">
                        <h2 class="h5">{{ column.title }}</h2>
                        <ul class="list-unstyled">
                            <li class="text-secondary" v-for="link in column.links"><a>{{ link }}</a></li>
                        </ul>
                    </div>
                    <div v-else v-for="columnSec in column">
                        <div>
                            <h2 class="h5">{{ columnSec.title }}</h2>
                            <ul class="list-unstyled">
                                <li class="text-secondary" v-for="link in columnSec.links"><a>{{ link }}</a></li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
            <img :src="logoImg" alt="LOGO">
        </div>
    </div>
    <div class="my-botBox">
        <div class="container d-flex justify-content-between align-items-center py-4">
            <div>
                <button class="my-btn">SIGN-UP NOW!</button>
            </div>
            <div class="d-flex gap-3 align-items-center">
                <div class="my-bluText">
                    FOLLOW US
                </div>
                <div>
                    <i class="fa-brands fa-facebook-f"></i>
                </div>
                <div>
                    <i class="fa-brands fa-twitter"></i>
                </div>
                <div>
                    <i class="fa-brands fa-youtube"></i>
                </div>
                <div>
                    <i class="fa-brands fa-pinterest"></i>
                </div>
                <div>
                    <i class="fa-solid fa-location-dot"></i>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.my-topBox{
    background-size: cover;
    overflow: hidden;
}

i{
    color: #303030;
    font-size: 1.3rem;
    background-color: gray;
    width: 35px;
    height: 35px;
    border-radius: 50%;
    text-align: center;
    line-height: 35px;
    transition: background .2s;
}

.my-btn:hover{
    background-color: #0282f9;
}

i:hover{
    background-color: white;
    cursor: pointer;
}

.my-btn{
    background-color: transparent;
    color: white;
    border: 2px solid #0282f9;
    padding: .5rem 1rem;
    transition: background .2s;
}

.my-bluText{
    color: #0282f9;
    font-weight: 500;
}

.my-botBox{
    background-color: #303030;
    color: white;
}

a{
    transition: color .2s;
}

a:hover{
    color: white !important;
    cursor: pointer;
}

img{
    margin-top: -120px;
    margin-bottom: -120px;
}
</style>
