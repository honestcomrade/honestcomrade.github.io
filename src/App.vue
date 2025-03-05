<script setup lang="ts">
interface Skill {
  title: string;
}

const technicalSkills: Skill[] = [
  { title: 'Full Stack Development' },
  { title: 'React - Vue.js' },
  { title: 'TypeScript - C#' },
];

const highlights: Skill[] = [
  { title: '0-1 Product Development' },
  { title: 'Technical Leadership' },
  { title: 'Continuous Delivery' }
];
</script>

<template>
  <div class="container">
    <h1>Joe Saraceno</h1>
    <p class="subtitle">Senior Software Engineer</p>
    
    <div class="content">
      <section class="intro">
        <p class="lead">
          Full-stack developer specializing in modern web applications and 0-1 product development, 
          with expertise in React, TypeScript, and C#. Focused on delivering scalable, customer-centric solutions.
        </p>
      </section>

      <section class="expertise">
        <h2>Technical Expertise</h2>
        <ul class="skills-list">
          <li v-for="skill in technicalSkills" :key="skill.title">
            {{ skill.title }}
          </li>
        </ul>
      </section>

      <section class="highlights">
        <h2>Professional Highlights</h2>
        <ul class="highlights-list">
          <li v-for="highlight in highlights" :key="highlight.title">
            {{ highlight.title }}
          </li>
        </ul>
      </section>

      <section class="current">
        <h2>Current Focus</h2>
        <p>
          Building modern web applications with a focus on developer experience,
          software quality, and continuous delivery. Leading technical initiatives
          to improve system architecture and team productivity.
        </p>
      </section>
    </div>
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
  font-size: 1.2rem;
  color: #666;
  margin-bottom: 1rem;
}

.content {
  margin: 2rem auto;
  max-width: 700px;
}

.intro {
  margin-bottom: 3rem;
}

.lead {
  font-size: 1.2rem;
  line-height: 1.6;
  color: #2c5364;
}

section {
  margin: 2.5rem 0;
}

h2 {
  font-size: 1.6rem;
  color: #2c5364;
  margin-bottom: 1.5rem;
}

p {
  margin: 1rem 0;
  line-height: 1.6;
}

.skills-list, .highlights-list {
  list-style: none;
  padding: 0;
  margin: 1.5rem 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
}

.skills-list li, .highlights-list li {
  font-size: 1.1rem;
  margin: 0.25rem;
}

.tech-list {
  font-weight: 600;
  color: #3498db;
  margin-top: 1rem;
}

.current {
  margin-top: 3rem;
}

@media (prefers-color-scheme: dark) {
  h1, h2 {
    color: #64b5f6;
  }

  .lead {
    color: #64b5f6;
  }

  .subtitle {
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
  
  section {
    margin: 1.5rem 0;
  }
  
  .intro {
    margin-bottom: 2rem;
  }

  h2 {
    margin-bottom: 1rem;
  }
}
</style>
