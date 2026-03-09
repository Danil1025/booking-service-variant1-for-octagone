<script setup lang="ts">
const emit = defineEmits<{
  (e: 'update:modelValue', value: boolean): void;
}>();

defineProps<{
  modelValue: boolean;
  title?: string;
}>();

const closeModal = () => {
  emit('update:modelValue', false);
};
</script>

<template>
  <Teleport to="body">
    <Transition name="modal">
      <div v-if="modelValue" class="modal-overlay" @click="closeModal">
        <div class="modal-container" @click.stop>
          
          <div class="modal-content">
            <h2 v-if="title" class="modal-title">{{ title }}</h2>
            <slot />
          </div>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.6);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  padding: 20px;
}

.modal-container {
  background: #FFFFFF;
  border-radius: 12px;
  padding: 30px;
  max-width: 482px;
  width: 100%;
  max-height: 90vh;
  overflow-y: auto;
  position: relative;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
}

.modal-close:hover {
  background: #E8E8E8;
  color: #000;
}

.modal-title {
  font-size: 24px;
  font-weight: 600;
  margin-bottom: 16px;
  color: #1a1a1a;
}

.modal-content {
  color: #333;
}

/* Анимация */
.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.3s ease;
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}

.modal-enter-active .modal-container,
.modal-leave-active .modal-container {
  transition: transform 0.3s ease;
}

.modal-enter-from .modal-container,
.modal-leave-to .modal-container {
  transform: scale(0.9) translateY(-20px);
}
</style>