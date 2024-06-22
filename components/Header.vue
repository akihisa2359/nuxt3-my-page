<template>
  <header>
    <nav>
      <ul>
        <li>Home</li>
        <li>About</li>
        <li>Skill</li>
        <li>Career</li>
        <li>Works</li>
        <li>Contacts</li>
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
}
</style>
