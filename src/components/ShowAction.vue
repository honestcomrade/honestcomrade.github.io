<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps<{
  content: string;
  hoverMessage?: string;
}>()

const showHoverTooltip = ref(false)
const showSuccessTooltip = ref(false)

const showHover = () => {
  if (!showSuccessTooltip.value) {
    showHoverTooltip.value = true
  }
}

const hideHover = () => {
  showHoverTooltip.value = false
}

const showSuccess = () => {
  showHoverTooltip.value = false
  showSuccessTooltip.value = true
  setTimeout(() => {
    showSuccessTooltip.value = false
  }, 2500)
}

defineExpose({ 
  showHover,
  hideHover,
  showSuccess
})
</script>

<template>
  <div class="tooltip-container">
    <div 
      v-if="showHoverTooltip && !showSuccessTooltip"
      class="tooltip hover-tooltip"
    >
      {{ hoverMessage || 'Click to copy' }}
    </div>
    
    <div 
      v-if="showSuccessTooltip"
      class="tooltip success-tooltip"
    >
      Copied&nbsp;<b>{{ props.content }}</b>&nbsp;!
    </div>
  </div>
</template>

<style scoped>
.tooltip-container {
  position: absolute;
  top: -35px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1000;
  pointer-events: none;
}

.tooltip {
  position: absolute;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  white-space: nowrap;
  background-color: var(--green);
  color: var(--dark-navy);
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 14px;
  left: 50%;
  transform: translateX(-50%);
}

.hover-tooltip {
  animation: fadeIn 0.2s ease-out forwards;
}

.success-tooltip {
  animation: fadeInOut 2.5s ease-in-out forwards;
}

@keyframes fadeIn {
  from { 
    opacity: 0;
    transform: translate(-50%, 10px);
  }
  to { 
    opacity: 1;
    transform: translate(-50%, 0);
  }
}

@keyframes fadeInOut {
  0% { 
    opacity: 0;
    transform: translate(-50%, 10px);
  }
  15% { 
    opacity: 1;
    transform: translate(-50%, 0);
  }
  85% { 
    opacity: 1;
    transform: translate(-50%, 0);
  }
  100% { 
    opacity: 0;
    transform: translate(-50%, -10px);
  }
}
</style> 