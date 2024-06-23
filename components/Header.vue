<template>
  <header>
    <nav>
      <ul>
        <li><a href="#">home</a></li>
        <li><a href="#about">about</a></li>
        <li><a href="#skill">skill</a></li>
        <li>career</li>
        <li><a href="#works">works</a></li>
        <li>contacts</li>
      </ul>
    </nav>
  </header>
</template>

<style scoped lang="scss">
header {
  height: 64px;
  width: 100%;
  background: rgba(100, 100, 100, 0.4);
  line-height: 64px;
  color: white;
}
nav {
  width: 80%;
  max-width: 768px;
  margin: 0 auto;
}
ul {
  display: flex;
  justify-content: space-between;

  li {
    font-size: $font-s;
    letter-spacing: 1px;
    @include media(sm) {
      font-size: $font-m;
    }
  }
}
</style>
