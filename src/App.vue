<template>
  <MenuPage/>

  <BannerPage :banner="'https://image.tmdb.org/t/p/original/'+results.backdrop_path" :rank="results.vote_average" :title="results.original_title" :synopsis="results.overview"/>

  <CarrouselPage Category="Popular" number="0"/>
  <CarrouselPage Category="Soon Available" number="1"/>
  <CarrouselPage Category="Top Ranked" number="2"/>
  <CarrouselPage Category="Now Playing" number="3"/>
  <CarrouselPage Category="5th Category" number="0"/>

  <FooterPage/>
</template>

<script>
import MenuPage from './components/Menu.vue'
import BannerPage from './components/Banner.vue'
import CarrouselPage from './components/Carrousel.vue'
import FooterPage from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    MenuPage,
    BannerPage,
    CarrouselPage,
    FooterPage,
  },

  data() {
    return {
      results: [],
    };
  },  

  async created() {
    await this.getMovies();
  },

  methods: {
    async getMovies() {
      let response = await fetch(
        "https://api.themoviedb.org/3/movie/popular/?api_key=98f3e6bc63ff40bda9789d766f877955"
      );
      const random = Math.ceil(Math.random()*19)
      const data = await response.json();
      this.results = data.results[random];
    },
  },
}
</script>

<style>

body{
  background: #121212;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

</style>
