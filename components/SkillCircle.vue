<template>
  <div>
    <div class="circle">
      <div class="circle-inner">hoge</div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  angle: { default: 360 },
});
</script>

<style scoped lang="scss">
.circle {
  position: relative;
  width: 80px;
  height: 80px;
  background: #ddd;
  border-radius: 50%;
  text-align: center;
  overflow: hidden;
  z-index: 1;
  &::before {
    content: "";
    display: block;
    position: absolute;
    top: 0;
    left: -40px;
    width: 80px;
    height: 80px;
    background: #1ec;
    transform: rotate(-30deg);
    transform-origin: right 40px;
    z-index: 2;
  }
  &::after {
    content: "";
    display: block;
    position: absolute;
    top: 0px;
    left: 40px;
    width: 80px;
    height: 80px;
    background: #1ec;
    transform-origin: left 40px;
    z-index: 3;
  }

  &-inner {
    position: absolute;
    top: 10px;
    left: 10px;
    width: 60px;
    height: 60px;
    background: white;
    border-radius: 50%;
    z-index: 4;
  }
}
</style>
