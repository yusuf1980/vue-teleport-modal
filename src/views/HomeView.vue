<script setup lang="ts">
import TheWelcome from '../components/TheWelcome.vue'
import {ref, markRaw} from 'vue'
import {useModal} from '../composables/useModal';
import Modal from '../components/Modal.vue'

const modal = useModal()

const openConfirm = () => {
  modal.component.value = markRaw(Modal);
  modal.showModal();
}
</script>

<template>
  <main>
    <!-- <h1 class="text-center">This is an Home</h1> -->
    <div class="flex justify-center items-center">
        <Teleport to="#modal">
          <Transition>
          <component :is="modal.component.value" v-if="modal.show.value" @close="modal.hideModal"></component>
        </Transition>
        </Teleport>
        <button @click="openConfirm" class="block text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800" type="button">
          Toggle modal
        </button>
    </div>
  </main>
</template>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
