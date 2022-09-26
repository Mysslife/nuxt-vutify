<template>
  <v-card>
    <v-img
      contain
      position="center"
      :src="`https://image.tmdb.org/t/p/w500${movie.poster_path}`"
    />
    <v-card-title class="d-block text-center" style="height: max-content">
      {{ movie.title }}
    </v-card-title>
    <v-card-text class="text-center">
      <v-row>
        <v-col cols="12" md="8" class="d-flex align-start">
          <v-rating
            :value="movie.vote_average / 2"
            half-increments
            length="5"
            color="yellow"
            dense
            readonly
            size="26"
          ></v-rating>
          <span class="grey--text text--darken text-h6 mx-2">
            {{ movie.vote_average }}
          </span>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: ["movie"],
};
</script>

<style></style>
