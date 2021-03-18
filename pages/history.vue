<template>
  <v-container>
    <v-row justify="center" align="center" class="mb-3">
      <v-spacer> </v-spacer>
      <v-col cols="8" class="text-center">
        <h1>Morphomusic</h1>
      </v-col>
      <v-col class="text-right" cols="2">
        <v-avatar v-if="pictureUrl" size="36">
          <img :src="pictureUrl" alt="プロフィール画像" />
        </v-avatar>
      </v-col>
    </v-row>
    <p class="text-center">
      <strong>{{ displayName }}</strong
      >さんの履歴
    </p>
    <v-btn v-if="!isinLine" depressed color="primary" @click="lineLogin">
      LOGIN
    </v-btn>
    <v-btn v-if="!isinLine" depressed color="primary" @click="lineLogout">
      LOGOUT
    </v-btn>
    <v-row>
      <v-col v-for="n in 20" :key="n" cols="6" sm="4">
        <v-card class="pa-2" outlined tile> One of three columns </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
let liff
if (process.client) {
  liff = require('@line/liff')
}
require('dotenv').config()
const { LIFFID } = process.env

export default {
  data() {
    return {
      isinLine: false,
      isLoggedin: false,
      userId: '',
      displayName: '',
      pictureUrl: '',
      idToken: '',
      liffErr: false,
      liffErrobj: null,
    }
  },
  head: {
    title: 'Morphomusic',
  },
  env: {
    LIFFID,
  },
  created() {
    if (process.client) {
      liff
        .init({
          liffId: process.env.LIFFID,
        })
        .then(() => {
          this.idToken = liff.getIDToken()
          this.initializeApp()
        })
        .catch((err) => {
          this.liffErr = true
          this.liffErrobj = err
        })
    }
  },
  methods: {
    initializeApp() {
      // if (liff.isInClient() && liff.isLoggedIn()) {
      if (liff.isLoggedIn()) {
        this.isinLine = true
        this.getProfile()
      }
    },
    getProfile() {
      liff
        .getProfile()
        .then((profile) => {
          this.userId = profile.userId
          this.displayName = profile.displayName
          this.pictureUrl = profile.pictureUrl
        })
        .catch((err) => {
          // console.log('error', err)
          alert('ユーザー情報の取得に失敗しました')
          print(err)
        })
    },
    // 開発用
    lineLogin() {
      if (!liff.isLoggedIn()) {
        liff.login()
      }
    },
    lineLogout() {
      liff.logout()
    },
  },
}
</script>
