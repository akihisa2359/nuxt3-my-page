<template>
  <section>
    <div class="works-page container">
      <h2>works</h2>
      <div class="works">
        <div class="work-wrapper">
          <h3 class="title">this site (Developed using Nuxt.js)</h3>
          <div class="work" @click="selectedWork = 'work1'">
            <img src="/public/work1.png" />
          </div>
          <span class="info">タップでモーダルが開きます</span>
        </div>
        <div class="work-wrapper">
          <h3 class="title">todo (Developed using Next.js)</h3>
          <div class="work" @click="selectedWork = 'work2'">
            <img src="/public/work2.png" />
          </div>
          <span class="info">タップでモーダルが開きます</span>
        </div>
        <div class="work-wrapper">
          <h3 class="title">line-login (Developed using Nuxt.js)</h3>
          <div class="work" @click="selectedWork = 'work3'">
            <img src="/public/work3.png" />
          </div>
          <span class="info">タップでモーダルが開きます</span>
        </div>
      </div>
    </div>

    <WorksDetailModal :work="selectedWork" @close="selectedWork = null" />
  </section>
</template>

<script setup>
// import ThisSiteModal from "/components/Works/ThisSiteModal.vue";

const selectedWork = ref(null);
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
section {
  color: #777;
}
.container {
  width: 100%;
  max-width: $width-sm;
  margin: 0 auto;
}

h2 {
  padding: 40px;
  letter-spacing: 12px;
  text-align: center;
  color: #96bdb9;
}

.works {
  margin: 40px 0;
  .work-wrapper {
    margin-bottom: 80px;
    .title {
      font-size: $font-m;
      letter-spacing: 2px;
      margin-bottom: 8px;
      margin-left: 4px;
      @include media(sm) {
        margin-left: 0px;
      }
    }
    span.info {
      font-size: $font-xs;
      margin-left: 4px;
      @include media(sm) {
        margin-left: 0px;
      }
    }
    .work {
      width: 100%;
      height: 200px;

      img {
        width: 100%;
        height: 200px;
        box-shadow: rgba(15, 15, 15, 0.2) 2px 2px 4px 2px;
        object-fit: cover;
        cursor: pointer;
        transition: filter 0.3s ease;
        &:hover {
          filter: brightness(0.8);
        }
      }
    }
  }
}
</style>
