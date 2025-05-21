<script setup lang="ts">
import { ref } from 'vue'

const visible = ref(false)

const props = defineProps<{
  content: string
}>()

const show = () => {
  visible.value = true
  setTimeout(() => {
    visible.value = false
  }, 2500)
}

defineExpose({ show })
</script>

<template>
  <div 
    v-if="visible"
    class="copied-indicator"
  >
    Copied&nbsp;<b>{{ props.content }}</b>&nbsp;!
  </div>
</template>

<style scoped>
.copied-indicator {
  position: absolute;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  white-space: nowrap;
  top: -55px;
  left: 50%;
  transform: translateX(-50%);
  background-color: var(--green);
  color: var(--dark-navy);
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 14px;
  z-index: 1000;
  animation: fadeInOut 2.5s ease-in-out forwards;
}

@keyframes fadeInOut {
  0% { opacity: 0; transform: translate(-50%, 10px); }
  15% { opacity: 1; transform: translate(-50%, 0); }
  85% { opacity: 1; transform: translate(-50%, 0); }
  100% { opacity: 0; transform: translate(-50%, -10px); }
}
</style> 