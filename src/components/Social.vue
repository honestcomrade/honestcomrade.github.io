<script setup lang="ts">
import { ref } from 'vue'
import ShowCopied from './ShowCopied.vue'

const props = defineProps<{
  url: string;
  icon: string;
  label: string;
  addCopyClick: boolean;
}>()

const showCopiedRef = ref()

const handleClick = async (e: Event) => {
  e.preventDefault()
  try {
    const input = document.createElement('input')
    input.value = props.url
    document.body.appendChild(input)
    
    input.select()
    document.execCommand('copy')
    
    document.body.removeChild(input)
    
    showCopiedRef.value?.show()
  } catch (err) {
    console.error('Failed to copy:', err)
  }
}
</script>

<template>
  <div class="social-container">
    <span   
      v-if="addCopyClick"
      class="social-icon"
      @click="handleClick">
      <svg viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
        <path :d="icon" />
      </svg>
    </span>
    <a 
      v-else
      :href="url"
      target="_blank"
      rel="noopener noreferrer"
      class="social-icon"
    >
      <svg viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
        <path :d="icon" />
      </svg>
    </a>
    <ShowCopied :content="url" ref="showCopiedRef" />
  </div>
</template>

<style scoped>
.social-container {
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.social-icon {
  color: var(--light-slate);
  transition: color 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

.social-icon:hover {
  color: var(--green);
}

</style> 