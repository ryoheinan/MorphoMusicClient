<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6" class="text-center">
      <div class="text-center mb-5">
        <v-avatar size="200" tile>
          <img src="~/assets/img/logo.jpg" />
        </v-avatar>
        <h1>Morphomusic</h1>
        <p>あなたの音楽の幅を広げるLINE Bot</p>
        <div
          class="line-it-button"
          data-lang="ja"
          data-type="friend"
          data-lineid="@748mkzdd"
          style="display: none"
        ></div>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  head: {
    script: [
      {
        src:
          'https://www.line-website.com/social-plugins/js/thirdparty/loader.min.js',
        body: true,
      },
    ],
  },
}
</script>
