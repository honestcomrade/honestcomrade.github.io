<script setup lang="ts">
interface Skill {
  title: string;
}

const technicalSkills: Skill[] = [
  { title: 'React + Vue.js' },
  { title: 'TypeScript + C#' },
  { title: 'Full Stack Development' },
  { title: 'FHIR Integrations' }
];

const highlights: Skill[] = [
  { title: '0-1 Product Development' },
  { title: 'Technical Leadership' },
  { title: 'Continuous Delivery' },
  { title: 'Collaboration' }
];

const socials = [
  { icon: 'github', url: '#', label: 'GitHub' },
  { icon: 'linkedin', url: '#', label: 'LinkedIn' }
];
</script>

<template>
  <div class="container">
    <div class="grid">
      <div class="left-side">
        <div class="name-intro">
          <h1>Joe Saraceno</h1>
        </div>
        <h2 class="big-heading">Full-stack engineer crafting modern web solutions.</h2>
        <p class="lead">
          I'm a seasoned software developer with a passion for building products from 0-1, with expertise in React, TypeScript, and C#. Focused on delivering scalable cloud products, with HIPAA experience and years of successful healthcare system integrations.
        </p>
      </div>
      <div class="right-side">
        <section class="expertise">
          <h3 class="section-heading">Technical Expertise</h3>
          <ul class="skills-list">
            <li v-for="skill in technicalSkills" :key="skill.title">
              <span class="skill-bullet">—</span>{{ skill.title }}
            </li>
          </ul>
        </section>

        <section class="highlights">
          <h3 class="section-heading">Professional Highlights</h3>
          <ul class="highlights-list">
            <li v-for="highlight in highlights" :key="highlight.title">
              <span class="skill-bullet">—</span>{{ highlight.title }}
            </li>
          </ul>
        </section>

        <section class="current">
          <h3 class="section-heading">Current Focus</h3>
          <p>
            Building modern web applications with a focus on software quality, developer experience,
            and continuous delivery. Leading technical initiatives to improve system architecture, team productivity, and customer value.
          </p>
        </section>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  margin-top: 2rem;
  width: 100%;
}

.grid {
  display: grid;
  grid-template-columns: 2fr 3fr;
  gap: 50px;
  align-items: start;
}

.left-side {
  position: sticky;
  top: 2rem;
}

.right-side {
  padding-top: 1rem;
  counter-reset: section;
}

h1 {
  font-size: clamp(40px, 5vw, 50px);
  margin: 0 0 25px;
  color: var(--lightest-slate);
  font-weight: 600;
  line-height: 1.1;
}

.big-heading {
  font-size: clamp(34px, 5vw, 38px);
  margin: 0;
  color: var(--light-slate);
  font-weight: 600;
  line-height: 1.1;
  position: relative;
}

.big-heading::before {
  content: '';
  position: absolute;
  left: -20px;
  width: 4px;
  height: 50%;
  background-color: var(--green);
  opacity: 0.5;
  border-radius: 2px;
  transform: translateY(50%);
}

.section-heading {
  display: flex;
  align-items: center;
  position: relative;
  margin: 10px 0 20px;
  width: 100%;
  font-size: clamp(20px, 4vw, 24px);
  color: var(--lightest-slate);
  white-space: nowrap;
}

.section-heading::before {
  content: "0" counter(section) ".";
  counter-increment: section;
  margin-right: 10px;
  color: var(--green);
  font-family: monospace;
  font-size: 0.9em;
  font-weight: 400;
  opacity: 0.8;
}

.section-heading::after {
  content: "";
  display: block;
  position: relative;
  width: 100%;
  height: 1px;
  margin-left: 20px;
  background-color: var(--lightest-navy);
}

.lead {
  margin: 2rem 0 0;
  max-width: 540px;
  color: var(--slate);
  font-size: clamp(14px, 4vw, 16px);
  line-height: 1.5;
}

section {
  margin: 0 0 3rem;
}

p {
  margin: 0.75rem 0;
  line-height: 1.6;
  color: var(--slate);
}

.skills-list, .highlights-list {
  list-style: none;
  padding: 0;
  margin: 0.75rem 0;
  display: grid;
  grid-template-columns: repeat(2, minmax(140px, 200px));
  gap: 0 10px;
  overflow: hidden;
}

.skills-list li, .highlights-list li {
  position: relative;
  margin-bottom: 6px;
  padding-left: 12px;
  font-size: 0.95rem;
  color: var(--slate);
  transition: transform 0.2s ease;
}

.skills-list li:hover, .highlights-list li:hover {
  transform: translateX(4px);
  color: var(--green);
}

.skill-bullet {
  position: absolute;
  left: 0;
  color: var(--green);
  font-size: 0.4rem;
  line-height: 20px;
  font-weight: 400;
  opacity: 0.8;
}

.current .section-heading,
.current p {
  padding: 0;
  position: relative;
}


.social-links {
  display: flex;
  gap: 2rem;
  margin-bottom: 25px;
}

.social-icon {
  color: var(--light-slate);
  font-size: 1.5rem;
  transition: color 0.2s ease;
  padding: 12px;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 24px;
  height: 24px;
}

.social-icon:hover {
  color: var(--green);
}

@media (max-width: 768px) {
  .grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .left-side {
    position: relative;
    top: 0;
  }

  .container {
    margin-top: 1.5rem;
  }

  section {
    margin: 0 0 2.5rem;
  }

  .current {
    padding: 1.25rem 0;
  }

  .current::before {
    left: -12px;
    right: -12px;
  }
}

@media (max-width: 480px) {
  .skills-list, .highlights-list {
    grid-template-columns: 1fr;
  }

  section {
    margin: 0 0 2rem;
  }

  .current {
    padding: 1rem 0;
  }

  .current::before {
    left: -10px;
    right: -10px;
  }
}

.name-intro {
  display: flex;
  align-items: baseline;
  gap: 0.5rem;
  margin-bottom: 25px;
  white-space: nowrap;
}

.name-intro span {
  color: var(--slate);
  font-size: clamp(14px, 4vw, 16px);
}

.name-intro h1 {
  margin: 0;
  white-space: nowrap;
}

.left-side > p:first-child {
  color: var(--slate);
  font-size: clamp(24px, 4vw, 32px);
  margin: 0 0 0.5rem;
}
</style>




