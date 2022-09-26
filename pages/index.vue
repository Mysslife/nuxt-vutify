<template>
  <div>
    <v-container>
      <SectionTitle :top="true" title="Popular Movies" />
      <v-row v-if="movies.length">
        <v-col cols="12" sm="6" md="4" v-for="movie in movies" :key="movie.id">
          <MovieCard :movie="movie" />
        </v-col>
      </v-row>

      <SectionTitle title="Upcoming Movies" />
      <v-row v-if="upcomingMovies.length">
        <v-col
          cols="12"
          sm="6"
          md="4"
          v-for="movie in upcomingMovies"
          :key="movie.id"
        >
          <MovieCard :movie="movie" />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import MovieCard from "../components/MovieCard.vue";
import SectionTitle from "../components/SectionTitle.vue";
export default {
  async asyncData({ $axios }) {
    try {
      const popularMovies = await $axios.$get(
        "movie/popular?api_key=775bb765d8690e3527a89a6aee9f30e0&language=en-US&page=1"
      );

      const upcomingMovies = await $axios.$get("movie/upcoming");

      return {
        movies: popularMovies.results.slice(0, 10),
        upcomingMovies: upcomingMovies.results.slice(0, 10),
      };
    } catch (err) {
      console.log(err);
    }
  },
  components: { MovieCard, SectionTitle },
};
</script>
