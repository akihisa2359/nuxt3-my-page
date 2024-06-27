<template>
  <div class="star-container">
    <div class="star-rating">
      <GeneralsIcon style="color: #ffd900" :fill="0">star</GeneralsIcon>
      <GeneralsIcon style="color: #ffd900" :fill="0">star</GeneralsIcon>
      <GeneralsIcon style="color: #ffd900" :fill="0">star</GeneralsIcon>
      <GeneralsIcon style="color: #ffd900" :fill="0">star</GeneralsIcon>
      <GeneralsIcon style="color: #ffd900" :fill="0">star</GeneralsIcon>
      <div class="star-rating-front" :style="style">
        <GeneralsIcon style="color: #ffd900" :fill="1">star</GeneralsIcon>
        <GeneralsIcon style="color: #ffd900" :fill="1">star</GeneralsIcon>
        <GeneralsIcon style="color: #ffd900" :fill="1">star</GeneralsIcon>
        <GeneralsIcon style="color: #ffd900" :fill="1">star</GeneralsIcon>
        <GeneralsIcon style="color: #ffd900" :fill="1">star</GeneralsIcon>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  score: { default: 0 },
});
const style = computed(() => ({
  width: `${props.score * 20}px`,
}));
</script>

<style scoped lang="scss">
.star-rating {
  position: relative;

  &-front {
    position: absolute;
    top: 0;
    left: 0;
    overflow: hidden;
    display: flex;
  }

  * {
    font-size: 20px;
  }
}
</style>
