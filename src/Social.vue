<template>
  <a href="{{ url }}"
    aria-label="{{ label }}"
    target="_blank"
    rel="noopener noreferrer"
    class="social-icon">
    <slot name="icon"></slot>
  </a>
</template>