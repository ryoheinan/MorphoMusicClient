<template>
  <v-container>
    <v-row justify="center" align="center">
      <v-col cols="12" sm="8" md="6" class="text-center">
        <div class="mb-5">
          <h1>Morphomusic</h1>
        </div>
      </v-col>
    </v-row>
    <v-row>
      <v-col v-for="n in 20" :key="n" cols="6" sm="4">
        <v-card class="pa-2" outlined tile> One of three columns </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import liff from '@line/liff'

export default {
  head: {
    title: 'Morphomusic',
  },
  mounted() {
    liff.init()
  },
}
</script>
