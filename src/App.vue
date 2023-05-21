<script>
import LogoNavbar from './components/LogoNavbar.vue'
import InfolistBar from './components/InfolistBar.vue'
import ColumnFooterWithBgAndLogo from './components/ColumnFooterWithBgAndLogo.vue'

export default {
  components: {
    LogoNavbar,
    InfolistBar,
    ColumnFooterWithBgAndLogo
  },
  data() {
    return {
      navElementsData: [
        'CHARACTERS', 
        'COMICS', 
        'MOVIES', 
        'TV', 
        'GAMES', 
        'COLLECTIBLES', 
        'VIDEOS', 
        'FANS', 
        'NEWS', 
        'SHOP'
      ],
      infolistBarData: [
        {
          name: "DIGITAL COMICS",
          imgFile: "buy-comics-digital-comics.png"
        },
        {
          name: "DC MERCHANDISE",
          imgFile: "buy-comics-merchandise.png"
        },
        {
          name: "SUBSCRIPTION",
          imgFile: "buy-comics-subscriptions.png"
        },
        {
          name: "COMIC SHOP LOCATOR",
          imgFile: "buy-comics-shop-locator.png"
        },
        {
          name: "DC POWER VISA",
          imgFile: "buy-dc-power-visa.svg"
        }
      ],
      columnsFooter: [
        [
          {
            title: "DC COMICS",
            links: [
              "Characters",
              "Comics",
              "Movies",
              "TV",
              "Games",
              "Videos",
              "News"
            ]
          },
          {
            title: "SHOP",
            links: [
              "Shop DC",
              "Shop DC Collectibles"
            ]
          }
        ],
        {
          title: "DC",
          links: [
            "Terms Of Use",
            "Privacy Policy (New)",
            "Ad Choices",
            "Advertising",
            "Jobs",
            "Subscriptions",
            "Talent Workshops",
            "CPSC Certificates",
            "Ratings",
            "Shop Help",
            "Contact Us"
          ]
        },
        {
          title: "SITES",
          links: [
            "DC",
            "MAD Magazine",
            "DC Kids",
            "DC Universe",
            "DC Power Visa"
          ]
        }
      ]
    }
  },
  methods: {
    logga() {
      console.log("Caricato il componente App, che ha richiamato il metodo 'logga()'");
    }
  },
  mounted() {
    this.logga();
  }
}
</script>

<template>

  <header>
    <div class="container">
        <LogoNavbar logoPath="./src/assets/img/dc-logo.png" :navElements="navElementsData" />
    </div>
  </header>

  <main>
    <div class="container text-white fs-3 py-5">
      Content goes here
    </div>
  </main>

  <footer>
    <div class="topBox">
      <div class="container">
        <InfolistBar :infolist="infolistBarData"/>
      </div>
    </div>
    <div class="botBox">
      <ColumnFooterWithBgAndLogo :columns="columnsFooter" bgImg="./src/assets/img/footer-bg.jpg" logoImg="./src/assets/img/dc-logo-bg.png"/>
    </div>
  </footer>

</template>

<style scoped>
main{
  background-color: #1c1c1c;
}

footer .topBox{
  background-color: #0282f9;
}
</style>
