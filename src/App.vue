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
    
    <div class="content">
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
  margin-top: 2rem;
}

h1 {
  font-size: 2.8rem;
  margin-bottom: 0.5rem;
  color: #2c5364;
  font-weight: 700;
}

.subtitle {
  font-size: 1.1rem;
  color: #666;
  margin-bottom: 2rem;
}

.content {
  margin: 2rem 0;
}

h2 {
  font-size: 1.8rem;
  color: #2c5364;
  margin-bottom: 1.5rem;
}

p {
  margin: 1rem 0;
  line-height: 1.6;
}

.tech-list {
  font-weight: 600;
  color: #3498db;
}

ul {
  list-style: none;
  padding: 0;
  margin: 1.5rem 0;
}

li {
  margin: 0.75rem 0;
  font-size: 1.1rem;
}

.coming-soon {
  font-style: italic;
  color: #666;
  margin-top: 2rem;
}

@media (prefers-color-scheme: dark) {
  h1, h2 {
    color: #64b5f6;
  }

  .subtitle, .coming-soon {
    color: #999;
  }

  .tech-list {
    color: #64b5f6;
  }
}

@media (max-height: 800px) {
  .container {
    margin-top: 1rem;
  }
  
  .content {
    margin: 1.5rem 0;
  }
  
  h2 {
    margin-bottom: 1rem;
  }
}
</style>
