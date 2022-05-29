<template>
  <div class="backdrop">
    <div></div>
    <dialog open>
      <slot></slot>
    </dialog>
  </div>
</template>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  z-index: 10;
  background-color: rgba(0, 0, 0, 0.077);
}
</style>