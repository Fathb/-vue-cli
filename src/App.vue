<template>
  <div id="app">
    <Header v-on:ganti-hero="gantiHero"></Header>
    <main>
      <p>daftar hero jadul mobile legends bang bang</p>
      <article v-if="!selectedHero">
      <Hero v-for="(item, id) of hero" :hero="item" :index="id" :key="item.id"></Hero>
      </article>
      <article v-else>
      <Hero :hero="selectedHero" :index=0 ></Hero>
      </article>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Footer from './components/Footer.vue';
  import Hero from './components/Hero.vue';

  export default {
    components: {
      Header,
      Footer,
      Hero
    },
    name: 'App',
    data() {
      return {
        hero: [
          {
            id: 1,
            nama: 'akai',
            type: 'tank initiator',
            gambar: 'akai.jpg'
          },
          {
            id: 2,
            nama: 'aurora',
            type: 'mage',
            gambar: 'aurora.jpg'
          },
          {
            id: 3,
            nama: 'bruno',
            type: 'mm',
            gambar: 'bruno.jpg'
          },
          {
            id: 4,
            nama: 'gatotkaca',
            type: 'tank',
            gambar: 'gatotkaca.png'
          },
          {
            id: 5,
            nama: 'Hilda',
            type: 'tank',
            gambar: 'hilda.jpg'
          },
          {
            id: 6,
            nama: 'lancelot',
            type: 'assasin',
            gambar: 'lancelot.jpg'
          },
          {
            id: 7,
            nama: 'lapu-lapu',
            type: 'fighter',
            gambar: 'lapulapu.jpg'
          }
        ],
        selectedHero: ''
      }
    },
    methods: {
      gantiHero() {
        this.selectedHero = this.randomHero ()
      },
      randomHero(){
        return this.hero[Math.floor (Math.random() * this.hero.length)]
      }
    }
  }
  </script>

  <style scoped>
    #app {
      font-family: Avenir,Helvetica, Arial, sans-serif;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      text-align: center;
      color: #2c3e50;
      margin-top: 60px;
    }
    article {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
    main {
      text-align: center;
    }
  </style>