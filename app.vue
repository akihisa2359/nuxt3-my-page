<template>
  <div>
    <NuxtRouteAnnouncer />
    <!-- <NuxtPage /> -->
    <Header class="header" />
    <MainVisual class="main" />
    <div class="contents">
      <About />
      <Skill />
      <div style="height: 100px" />
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
}
</style>
