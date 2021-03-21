<template>
  <v-row justify="center" align="center">
    <v-col cols="11" sm="8">
      <div class="text-center mb-5">
        <v-avatar size="200" tile>
          <img src="~/assets/img/logo.jpg" />
        </v-avatar>
        <h1>Morphomusic</h1>
        <p>あなたの音楽の幅を広げるLINE Bot</p>
        <a href="https://lin.ee/Wg3Fqsy"
          ><img
            src="https://scdn.line-apps.com/n/line_add_friends/btn/ja.png"
            alt="LINE友だち追加"
            height="36"
            border="0"
        /></a>
      </div>
      <section>
        <h2>Morphomusicとは？</h2>
        <p>
          MorphomusicはLINE上のメッセージを形態素解析して曲を返してくれるBotサービスです。<br />
        </p>
      </section>
      <section>
        <h2>Morphomusicの目的は？</h2>
        <p>
          LINEのメッセージをきっかけに新たな音楽の出会いを作ることができたらと思い開発しました。<br />
          また、Morphomusicはグループ内においても使用可能です。友だち・家族などのコミュニケーションのきっかけにもなるようなサービスとなっています。
        </p>
      </section>
      <section>
        <h2>これまでの楽曲情報一覧を見たいんだけど…</h2>
        <p>
          Morphomusicが入っているグループ内や個人チャットで「履歴」と送信すれば、履歴ページのURLが表示されます。<br />
          また、個人チャットのメニューからでもアクセス可能です。
        </p>
      </section>
      <section>
        <h2>Botがうるさいんだけど…</h2>
        <p>
          Morphomusicが入っているグループ内や個人チャットで「停止」と送信すれば、楽曲情報の返信を停止できます。返信を停止しても履歴ページには楽曲情報が追加されます<br />
          停止状態を解除したい時は、「解除」と送信してください。
        </p>
      </section>
    </v-col>
  </v-row>
</template>

<script>
export default {
  head: {},
}
</script>
