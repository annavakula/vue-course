<template>
  <div class="main-block">
    <button @click="showModal">Show Modal Window</button>
    <br><br><br>
    <label for="modalTitle">Title:</label>
    <input type="text" id="modalTitle" v-model="modalTitle">
    <br><br>
    <label for="modalMessage">Message</label>
    <input type="text" id="modalMessage" v-model="modalMessage">
    <br><br>
  </div>
  <Modal v-if="isModalOpen" :modal-title="modalTitle" :modal-message="modalMessage" @close="closeModal"></Modal>
</template>

<script>
import { defineComponent, ref } from "vue";
import Modal from '@/Modal.vue'

export default defineComponent({
  components: {Modal},
  setup() {

    const isModalOpen = ref(false);
    const modalTitle = ref('');
    const modalMessage = ref('');

    function showModal() {
      isModalOpen.value = true;
      // modalTitle.value = 'Default Title';
      // modalMessage.value = 'Default Message';
    }

    function closeModal() {
      isModalOpen.value = false;
      modalTitle.value = '';
      modalMessage.value = '';
    }

    return {
      isModalOpen,
      modalTitle,
      modalMessage,
      showModal,
      closeModal
    }
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
