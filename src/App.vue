<script setup lang="ts">
  import Social from './components/Social.vue'

  interface Skill {
    title: string;
  }

  interface Social {
    icon: string;
    url: string;
    label: string;
  }

  const technicalSkills: Skill[] = [
    { title: 'React + Vue.js' },
    { title: 'TypeScript + C#' },
    { title: 'Full Stack Development' },
    { title: 'FHIR Integrations' },
    { title: 'CI/CD' },
    { title: 'Cloud Architecture' }
  ];

  const highlights: Skill[] = [
    { title: '0-1 Product Development' },
    { title: 'Technical Leadership' },
    { title: 'Continuous Delivery' },
    { title: 'Collaboration' },
    { title: 'Agile Methodologies' },
    { title: 'Quality Focus' }
  ];

  const socials: Social[] = [
    { 
      icon: "M12 2C6.477 2 2 6.477 2 12c0 4.42 2.87 8.17 6.84 9.5.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34-.46-1.16-1.11-1.47-1.11-1.47-.91-.62.07-.6.07-.6 1 .07 1.53 1.03 1.53 1.03.87 1.52 2.34 1.07 2.91.83.09-.65.35-1.09.63-1.34-2.22-.25-4.55-1.11-4.55-4.92 0-1.11.38-2 1.03-2.71-.1-.25-.45-1.29.1-2.64 0 0 .84-.27 2.75 1.02.79-.22 1.65-.33 2.5-.33.85 0 1.71.11 2.5.33 1.91-1.29 2.75-1.02 2.75-1.02.55 1.35.2 2.39.1 2.64.65.71 1.03 1.6 1.03 2.71 0 3.82-2.34 4.66-4.57 4.91.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0012 2z",
      url: 'https://github.com/honestcomrade',
      label: 'GitHub'
    },
    { 
      icon: "M19 3a2 2 0 012 2v14a2 2 0 01-2 2H5a2 2 0 01-2-2V5a2 2 0 012-2h14m-.5 15.5v-5.3a3.26 3.26 0 00-3.26-3.26c-.85 0-1.84.52-2.32 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 011.4 1.4v4.93h2.79M6.88 8.56a1.68 1.68 0 001.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 00-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z",
      url: 'https://www.linkedin.com/in/joseph-saraceno-755860ba/',
      label: 'LinkedIn'
    },
    {
      icon: "M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z",
      url: 'josephasaraceno@gmail.com',
      label: 'Email',
    }
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
          Senior software engineer with a proven track record of architecting and delivering enterprise-scale applications. Leveraging expertise in React, TypeScript, and C# to build robust, scalable solutions that drive business value. Currently leading technical initiatives and mentoring teams while maintaining a hands-on approach to development.
        </p>
        <div class="social-links">
          <Social v-for="social in socials" 
            :label="social.label"
            :addCopyClick="social.label === 'Email'"
            :key="social.url" 
            :url="social.url"
            :icon="social.icon" 
          />
        </div>
      </div>
      <div class="right-side">
        <section class="expertise">
          <h3 class="section-heading">Technical Expertise</h3>
          <ul class="skills-list">
            <li v-for="skill in technicalSkills" :key="skill.title">
              <span class="skill-bullet">•</span>{{ skill.title }}
            </li>
          </ul>
        </section>

        <section class="highlights">
          <h3 class="section-heading">Professional Highlights</h3>
          <ul class="highlights-list">
            <li v-for="highlight in highlights" :key="highlight.title">
              <span class="skill-bullet">•</span>{{ highlight.title }}
            </li>
          </ul>
        </section>

        <section class="current">
          <h3 class="section-heading">Current Work</h3>
          <p>
            Building modern web applications with a focus on automation, continuous delivery and quality. Leading technical initiatives to improve system architecture, team productivity, and customer value. Leveraging AI to delivery quickly without sacrificing quality.
          </p>
        </section>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
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
  margin: 0 0 20px;
  width: 100%;
  font-size: clamp(20px, 4vw, 24px);
  color: var(--lightest-slate);
  white-space: nowrap;
}

.section-heading::before {
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
  margin-bottom: 8px;
  padding-left: 16px;
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
  font-size: 0.8rem;
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
  gap: 0.75rem;
  margin: 2rem 0 0;
  padding-left: 0;
}

.social-icon {
  color: var(--light-slate);
  font-size: 1.1rem;
  transition: color 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

.social-icon:hover {
  color: var(--green);
}

@media (max-width: 768px) {

  .left-side {
    position: relative;
    top: 0;
  }

  .container {
    padding: 1.5rem;
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

  .container {
    padding: 1rem;
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
}
</style>




