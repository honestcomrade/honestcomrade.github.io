<script setup lang="ts">
interface TechSkill {
  title: string;
}

const techSkills: TechSkill[] = [
  { title: 'Modern Frontend Architecture' },
  { title: 'Type-Safe Development' },
  { title: 'Clean, Maintainable Code' }
];
</script>

<template>
  <div class="container">
    <h1>Joe Saraceno</h1>
    <p class="subtitle">Software Engineer & Problem Solver</p>
    
    <div class="tech-stack">
      <h2>Coming Soon</h2>
      <p>This site is currently under development and will soon showcase my work using modern web technologies:</p>
      <p class="tech-list">Vue 3 • TypeScript • Vite</p>
      <p>The final version will demonstrate best practices in:</p>
      <ul>
        <li v-for="skill in techSkills" :key="skill.title">
          {{ skill.title }}
        </li>
      </ul>
    </div>

    <p class="coming-soon">Check back soon for the full experience!</p>
  </div>
</template>

<style scoped>
.container {
  text-align: center;
  margin-top: 4rem;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.subtitle {
  font-size: 1.2rem;
  color: #666;
  margin-bottom: 2rem;
}

.tech-stack {
  background: #f5f5f5;
  padding: 1.5rem;
  border-radius: 8px;
  margin: 2rem 0;
}

.tech-list {
  font-weight: 500;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  margin: 0.5rem 0;
}

.coming-soon {
  font-style: italic;
  color: #666;
  margin-top: 2rem;
}
</style>
