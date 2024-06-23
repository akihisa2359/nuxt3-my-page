<template>
  <Transition>
    <Generals-Modal v-if="isVisible" @close="emit('close')">
      <div class="content">
        <template v-if="work === 'work1'">
          <h3 class="title">当サイトです。</h3>
          <p class="comment">
            スペースを大きめにとり、メインビジュアルのゆったりした雰囲気に沿うように意識しました。
          </p>
          <p class="comment">制作期間：2日（20h）</p>
          <div class="iframe-wrapper">
            <iframe :src="workSrcs[work]" class="iframe-preview" />
          </div>
        </template>
        <template v-if="work === 'work2'">
          <h3 class="title">
            <a :href="workSrcs[work]" target="_blank"
              ><span class="link"
                >todoアプリ<Icon class="open-icon">open_in_new</Icon></span
              ></a
            >です。
          </h3>
          <p class="comment">
            Next.jsで0から実装したことがなかったため、学習のために作成しました。<br />
          </p>
          <p class="comment">制作期間：3日（22h）</p>
          <div class="iframe-wrapper">
            <iframe :src="workSrcs[work]" class="iframe-preview" />
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
  work1: "https://maki-nuxt-page.vercel.app/",
  work2: "https://maki-next-todo.vercel.app/",
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
  width: 80vw;
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
