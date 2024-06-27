<template>
  <div class="img-wrapper">
    <img src="/public/cat1.jpg" class="" />
    <div class="content-wrapper">
      <div class="content">
        <div class="name">Akihisa Makimoto</div>
        <div class="description">Web Developer</div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.img-wrapper {
  height: 100vh;
  width: 100vw;
  position: relative;

  img {
    height: 100%;
    width: 100%;
    object-fit: cover;
  }

  .content-wrapper {
    height: 100%;
    width: 100%;
    position: absolute;
    top: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    text-align: center;
    letter-spacing: 5px;
    text-shadow: #bbb 2px 3px;

    .content {
      width: 100%;

      .name {
        // font-family: "Pacifico";
        font-size: 24px;
        margin-bottom: 16px;
      }

      .description {
        font-size: 16px;
      }
    }
  }
}
.hoge {
  width: 100vw;
  height: 100vh;
  object-fit: cover;
  text-align: center;
}
p {
  color: $secondary;
}
</style>
