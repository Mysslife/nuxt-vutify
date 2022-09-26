<template>
  <v-toolbar :class="`${top ? '' : 'mt-6'}`" short flat>
    <v-toolbar-title> {{ title?.toUpperCase() }} </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn text color="pink"
      >See more
      <v-icon right> mdi-chevron-double-right </v-icon>
    </v-btn>
  </v-toolbar>
</template>

<script>
export default {
  props: ["top", "title"],
};
</script>

<style></style>
