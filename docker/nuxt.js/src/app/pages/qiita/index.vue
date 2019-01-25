<template>
  <section class="container">
    <div>
      <h1 class="title">
        Qiita APIへアクセス
      </h1>
      <p>Qiita APIから、Nuxt.jsのタグが付けられた投稿を取得してみる</p>
    </div>
  </section>
</template>

<script>
  export default {
    name: "qiita-index",
    async mounted() {
      console.log(JSON.stringify(await
        this.$axios.$get('https://qiita.com/api/v2/items?query=tag:nuxt.js'), true, '   ')
      )
    }
  }
</script>

