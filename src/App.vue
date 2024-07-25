<template>
  <div class="container mx-auto p-4">
    <h1 class="text-3xl font-bold mb-4">Películas de Star Wars</h1>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      <FilmList :films="films" @film-selected="selectFilm" />
      <FilmDetails v-if="selectedFilm" :film="selectedFilm" />
    </div>
  </div>
</template>

<script>
import FilmList from './components/FilmList.vue';
import FilmDetails from './components/FilmDetails.vue';

export default {
  components: {
    FilmList,
    FilmDetails
  },
  data() {
    return {
      films: [],
      selectedFilm: null
    };
  },
  mounted() {
    this.fetchFilms();
  },
  methods: {
    async fetchFilms() {
      const response = await fetch('https://swapi.dev/api/films/');
      const data = await response.json();
      this.films = data.results;
    },
    selectFilm(film) {
      this.selectedFilm = film;
    }
  }
}
</script>
