<template>
  <div class="container">
    <UserList />
  </div>
  <div class="container">
    <div class="circle" :class="{ animate: animatingCircle }"></div>
    <button @click="animateCircle">Animate</button>
  </div>

  <div class="container">
    <transition name="paragraph">
      <p v-if="paragraphVisible">Paragraph</p>
    </transition>
    <button @click="toggleParagraph">Switch</button>
  </div>

  <Modal :open="dialogIsVisible">
    <p>This is a test modal</p>
    <button @click="toggleModal">Close</button>
  </Modal>

  <div class="container">
    <button @click="toggleModal">Modal</button>
  </div>
</template>  

<script setup lang="ts">
import { ref } from 'vue';
import Modal from './components/Modal.vue';
import UserList from './components/UserList.vue';

const animatingCircle = ref(false)
const paragraphVisible = ref(false)
const dialogIsVisible = ref(false)

const animateCircle = () => {
  animatingCircle.value = true
}
const toggleParagraph = () => {
  paragraphVisible.value = !paragraphVisible.value
}
const toggleModal = () => {
  dialogIsVisible.value = !dialogIsVisible.value
}

</script>

<style>
* {
  box-sizing: border-box;
}
html {
  font-family: sans-serif;
}
body {
  margin: 0;
}
button {
  font: inherit;
  padding: 0.5rem 2rem;
  border: 1px solid #180081;
  border-radius: 30px;
  background-color: #000981;
  color: white;
  cursor: pointer;
}
button:hover,
button:active {
  background-color: #0b64a8;
  border-color: #0b64a8;
}
.circle {
  width: 8rem;
  height: 8rem;
  background-color: #2c5b8e;
  margin-bottom: 2rem;
  border-radius: 4rem;
}
.container {
  max-width: 40rem;
  margin: 2rem auto;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 2rem;
  border: 2px solid #ccc;
  border-radius: 12px;
}

.paragraph-enter-from {
  opacity: 0;
  transform: translateY(-30px);
}
.paragraph-enter-to {
  opacity: 1;
  transform: translateY(0);
}
.paragraph-enter-active {
  transition: all 0.3s ease-out;
}

.animate {
  /* transform: translateX(-100px) */
  animation: fade 0.3s ease-out forwards;
}

@keyframes fade {
  0% {
    transform: translateX(0)
  }
  70% {
    transform: translateX(-90px)
  }
  100% {
    transform: translateX(-100px)
  }
}
</style>