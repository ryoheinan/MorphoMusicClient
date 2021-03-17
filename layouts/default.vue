<template>
  <v-app>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer>
      <v-col class="text-center" cols="12"
        >&copy; {{ new Date().getFullYear() }} Morphomusic Team</v-col
      >
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {}
  },
}
</script>
