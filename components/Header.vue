<template>
  <header>
    <nav>
      <ul>
        <li>
          <a href="#home" @click.prevent="scrollToSection('home')">home</a>
        </li>
        <li>
          <a href="#about" @click.prevent="scrollToSection('about')">about</a>
        </li>
        <li>
          <a href="#skill" @click.prevent="scrollToSection('skill')">skill</a>
        </li>
        <li>career</li>
        <li>
          <a href="#works" @click.prevent="scrollToSection('works')">works</a>
        </li>
        <li>contacts</li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
const scrollToSection = (id) => {
  if (id === "home") {
    window.scrollTo({ top: 0, behavior: "smooth" });
  }

  const element = document.getElementById(id);
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
  }
};
</script>

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
