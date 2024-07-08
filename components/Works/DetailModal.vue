<template>
  <Transition>
    <Generals-Modal v-if="isVisible" @close="emit('close')">
      <div class="content">
        <template v-if="work === 'work1'">
          <h3 class="title">
            当サイトです。<a
              class="link"
              :href="workSrcs.work1.github"
              target="_blank"
              >github<GeneralsIcon class="open-icon"
                >open_in_new</GeneralsIcon
              ></a
            >
          </h3>
          <p class="comment">
            スペースを大きめにとり、メインビジュアルのゆったりした雰囲気に沿うように意識しました。
          </p>
          <p class="comment">制作期間：2日（20h）</p>
          <div class="iframe-wrapper">
            <iframe :src="workSrcs.work1.link" class="iframe-preview" />
          </div>
        </template>
        <template v-if="work === 'work2'">
          <h3 class="title">
            <a class="link" :href="workSrcs.work2.link" target="_blank"
              >todoアプリ<GeneralsIcon class="open-icon"
                >open_in_new</GeneralsIcon
              ></a
            >です。<a class="link" :href="workSrcs.work2.github" target="_blank"
              >github<GeneralsIcon class="open-icon"
                >open_in_new</GeneralsIcon
              ></a
            >
          </h3>
          <p class="comment">
            Next.jsで0から実装したことがなかったため、学習のために作成しました。<br />
          </p>
          <p class="comment">制作期間：3日（22h）</p>
          <div class="iframe-wrapper">
            <iframe :src="workSrcs.work2.link" class="iframe-preview" />
          </div>
        </template>
        <template v-if="work === 'work3'">
          <h3 class="title">
            <a class="link" :href="workSrcs[work].link" target="_blank"
              >LINEログインのデモ<GeneralsIcon class="open-icon"
                >open_in_new</GeneralsIcon
              ></a
            >です。<a class="link" :href="workSrcs[work].github" target="_blank"
              >github<GeneralsIcon class="open-icon"
                >open_in_new</GeneralsIcon
              ></a
            >
          </h3>
          <p class="comment">
            Nuxt.jsでLINEログインの機能を実装しました。
            サーバーにはNuxt.jsのサーバーAPIを利用しています。
          </p>
          <p class="comment">制作期間：2日（16h）</p>
          <p class="comment">
            所感：<br />
            cookieやトークンを扱うに当たってサーバーとクライアントの使い分けに配慮しました。<br />
            その分、それを実現するためのNuxt.jsでの実装に苦戦しました。
          </p>
          <div style="text-align: center">
            <img
              src="/public/work3.gif"
              style="width: 300px; overflow-y: hidden"
            />
          </div>
        </template>
      </div>
    </Generals-Modal>
  </Transition>
</template>

<script setup>
const emit = defineEmits(["close"]);
const props = defineProps({
  work: { default: null },
});

const workSrcs = {
  work1: {
    link: "https://maki-nuxt-page.vercel.app/",
    github: "https://github.com/akihisa2359/Next-todo",
  },
  work2: {
    link: "https://maki-next-todo.vercel.app/",
    github: "https://github.com/akihisa2359/nuxt3-my-page",
  },
  work3: {
    link: "https://maki-line-login-demo.vercel.app/",
    github: "https://github.com/akihisa2359/line-login-demo",
  },
};
const isVisible = computed(() => {
  return props.work !== null;
});
</script>

<style scoped lang="scss">
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

.content {
  font-size: $font-m;
  color: #777;
  padding: 24px;
  height: 50vh;
  width: 90vw;
  overflow-y: auto;
  @include media(sm) {
    height: 70vh;
    width: 50vw;
    min-width: 500px;
  }

  .title {
    margin-bottom: $space-m;
    .link {
      border-bottom: solid 1px #ddd;
    }
  }
  .comment {
    margin-bottom: $space-m;
  }

  .open-icon {
    font-size: $font-m;
  }

  .iframe-wrapper {
    // height: 100%;
    height: calc(100% - 120px);
    iframe {
      width: 100%;
      height: 100%;
    }
  }
}
</style>
