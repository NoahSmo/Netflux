<template>
  <div id="row">
    <h2>{{ Category }}</h2>
    <div id="carrousel">
      <!-- <MyCard
        v-for="result in results"
        v-bind:key="result.id"
        :title="result.original_title"
        :img="'https://image.tmdb.org/t/p/original' + result.poster_path"
      /> -->

      <MyCard
        v-for="result in results"
        v-bind:key="result.id"
        :title="result.original_title"
        :img="'https://image.tmdb.org/t/p/original' + result.poster_path"
      />
    </div>
  </div>
</template>

<script>
import MyCard from "./Card.vue";

export default {
  name: "CarrouselPage",
  components: {
    MyCard,
  },

  props: {
    Category: String,
    number: String,
  },

  data() {
    return {
      results: [],
      genre: ["popular","upcoming","top_rated","now_playing"],
    };
  },

  async created() {
    await this.getMovies();
  },

  methods: {
    async getMovies() {
      // const random = Math.ceil(Math.random()*3)
      
      // let Genre = this.genre[random]
      let Genre = this.genre[this.number]

      console.log(this.number)
      
      
      let link =
        "https://api.themoviedb.org/3/movie/" +
        Genre +
        "/?api_key=98f3e6bc63ff40bda9789d766f877955";
      let response = await fetch(link);

      const data = await response.json();

      console.log(data.results);

      this.results = data.results;

      return data.results;
    },
  },
};
</script>

<style scoped>
h2 {
  text-align: left;
  width: fit-content;
  position: relative;
  left: 1em;
  bottom: 0.4em;
  margin: 0;
  color: #fff;
}

#row{
  margin-bottom: 5vh;
}

#carrousel {
  overflow-y: overlay;
  display: flex;
  gap: 1em;
  /* width: 98%; */
  margin: auto;
  color: black;
}

::-webkit-scrollbar {
  width: 0;
  background: transparent;
}

::-webkit-scrollbar-thumb {
  background: transparent;
  height: 100%;
}
</style>