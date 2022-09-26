<template>
  <div>
    <v-toolbar>
      <v-toolbar-title>
        <v-icon size="64px" color="pink">mdi-video</v-icon>
        Movie DB
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-toolbar-items>
        <v-btn
          link
          text
          v-for="(item, index) in items"
          :key="index"
          :to="item.link"
        >
          {{ item.title }}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { title: "Movies", link: "/" },
        { title: "TV Series", link: "/tvseries" },
        { title: "Actors", link: "/actors" },
      ],
    };
  },
};
</script>
