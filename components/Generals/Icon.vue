<!-- サイズ(font-size)や色(color)は利用側で指定してください -->
<template>
  <span :style="style" class="material-symbols-outlined">
    <slot />
  </span>
</template>

<script setup>
const props = defineProps({
  fill: { default: 0 },
});

const style = computed(() => ({
  fontVariationSettings: `"FILL" ${props.fill}, "wght" 400, "GRAD" 0, "opsz" 24`,
}));
</script>

<style scoped lang="scss"></style>
