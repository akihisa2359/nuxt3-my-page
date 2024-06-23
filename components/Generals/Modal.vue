<template>
  <div class="modal-overlay" @click="closeModal">
    <div class="modal" @click="onClick">
      <slot />
    </div>
  </div>
</template>
<script setup>
const emit = defineEmits(["close"]);

const closeModal = () => {
  emit("close");
};

const onClick = (event) => {
  event.stopPropagation();
};

const handleKeydown = (event) => {
  if (event.key === "Escape") {
    closeModal();
  }
};

onMounted(() => {
  window.addEventListener("keydown", handleKeydown);
  document.body.classList.add("modal-open");
});

onUnmounted(() => {
  window.removeEventListener("keydown", handleKeydown);
  document.body.classList.remove("modal-open");
});
</script>

<style scoped lang="scss">
.modal-overlay {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.6);
  z-index: 9999;

  display: flex;
  justify-content: center;
  align-items: center;

  .modal {
    background: white;
    min-height: 100px;
    min-width: 100px;
    border-radius: 4px;
  }
}
</style>
