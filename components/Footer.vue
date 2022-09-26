<template>
  <v-footer padless dark>
    <v-card class="flex text-center" flat dense title>
      <v-card-text class="gray darken-4 d-flex flex-column align-center">
        <strong class="subheading">Connect with us via Social!</strong>
        <div>
          <v-btn
            dark
            icon
            v-for="(icon, index) in socialIcons"
            :key="index"
            target="_blank"
            :href="icon.link"
            class="mx-1"
          >
            <v-icon :size="icon.size + 'px'">{{ icon.name }}</v-icon>
          </v-btn>
        </div>
      </v-card-text>
      <v-card-text class="py-2 white--text text-center">
        {{ new Date().getFullYear() }} - <strong>MovieDB</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data() {
    return {
      socialIcons: [
        { name: "mdi-youtube", size: 28, link: "https://www.instagram.com/" },
        { name: "mdi-instagram", size: 20, link: "https://www.instagram.com/" },
        {
          name: "mdi-facebook",
          size: 24,
          link: "https://www.facebook.com/edward.nguyen.0902/",
        },
      ],
    };
  },
};
</script>

<style></style>
