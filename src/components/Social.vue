<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps<{
  url: string;
  icon: string;
  label: string;
  email: boolean;
}>()

const showCopied = ref(false)

const handleClick = async (e: Event) => {
  if (props.email) {
    e.preventDefault()
    try {
      // Create a temporary input element
      const input = document.createElement('input')
      input.value = props.url
      document.body.appendChild(input)
      
      // Select and copy the text
      input.select()
      document.execCommand('copy')
      
      // Clean up
      document.body.removeChild(input)
      
      // Show success message
      showCopied.value = true
      setTimeout(() => {
        showCopied.value = false
      }, 2000)
    } catch (err) {
      console.error('Failed to copy:', err)
    }
  }
}
</script>

<template>
  <a :href="url"
    target="_blank"
    rel="noopener noreferrer"
    class="social-icon"
    @click="handleClick">
    <svg viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
      <path :d="icon" />
    </svg>
    <span v-if="showCopied" class="copied-tooltip">Copied!</span>
  </a>
</template>

<style scoped>
.social-icon {
  color: var(--light-slate);
  transition: color 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.social-icon:hover {
  color: var(--green);
}

.copied-tooltip {
  position: absolute;
  top: -35px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--green);
  color: var(--dark-navy);
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 0.8rem;
  white-space: nowrap;
  animation: fadeInOut 2s ease-in-out;
}

@keyframes fadeInOut {
  0% { opacity: 0; transform: translate(-50%, 10px); }
  20% { opacity: 1; transform: translate(-50%, 0); }
  80% { opacity: 1; transform: translate(-50%, 0); }
  100% { opacity: 0; transform: translate(-50%, -10px); }
}
</style> 