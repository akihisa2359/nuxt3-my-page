<template>
  <div>
    <NuxtRouteAnnouncer />
    <!-- <NuxtPage /> -->
    <Header class="header" />
    <MainVisual class="main" />
    <div class="contents">
      <About />
      <Skill />
    </div>
  </div>
</template>

<style scoped lang="scss">
.header {
  position: fixed;
  top: 0;
  z-index: 10;
}

.main {
  position: fixed;
  top: 0;
  z-index: -1;
}

.contents {
  background: white;
  position: relative;
  top: 100vh;
  // z-index: 1;
}
</style>
