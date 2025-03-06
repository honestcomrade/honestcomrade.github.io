<script setup lang="ts">
  defineProps<{
    url: string;
    icon: string;
  }>()
</script>

<template>
  <a :href="url"
    target="_blank"
    rel="noopener noreferrer"
    class="social-icon">
    <svg viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
      <path :d="icon" />
    </svg>
  </a>
</template>

<style scoped>
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