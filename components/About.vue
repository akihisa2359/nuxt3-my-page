<template>
  <section>
    <div class="container">
      <h2 class="title">about</h2>
      <div class="description">
        <p class="mb-m">
          大阪府出身、東京都在住のwebエンジニア。
          大学では英語の教師になるために教職課程に進み留学を経験するも、ITの技術に惹かれ新卒としてSIerに就職。
        </p>
        <p>
          現在は人材会社でヒアリングや設計を始め、AWSのインフラ構築、フロントエンド・バックエンドの開発まで幅広く対応しています。
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
section {
  display: flex;
  justify-content: center;
  font-family: sans-serif;
  font-size: 14px;
  padding: 112px 32px 0;
  margin-bottom: 112px;

  .container {
    max-width: $width-sm;

    .description {
      line-height: 32px;
      letter-spacing: 2px;
    }
  }
}
.title {
  letter-spacing: 12px;
  margin-bottom: 80px;
  text-align: center;
  color: #96bdb9;
}
</style>
