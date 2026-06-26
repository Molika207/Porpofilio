<template>
  <header>
    <nav>
      <a href="#" class="logo">Molika.</a>
      <ul>
        <li><a href="#stack">Tech Stack</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <a href="mailto:lonmolika303@gmail.com" class="nav-cta">Hire Me</a>
    </nav>
  </header>

  <main>
    <section class="hero-section">
      <div class="hero-copy">
        <p class="eyebrow">QA Frontend & UX/UI Portfolio</p>
        <h1 class="hero-name-code" aria-label="Hi, I'm Molika Lon">
          <span class="typed-name">{{ typedName }}</span>
          <span class="typing-cursor" aria-hidden="true"></span>
        </h1>
        <p class="hero-role">
          I test and improve frontend experiences with careful QA, clean interfaces, and user-focused UX/UI decisions.
        </p>

        <div class="role-parts" aria-label="Portfolio focus areas">
          <span>QA</span>
          <span>Frontend</span>
          <span>UX/UI</span>
        </div>

        <div class="hero-buttons">
          <a href="#projects" class="btn btn-primary">View Projects</a>
          <a href="#contact" class="btn btn-outline">Get in Touch</a>
          <a :href="cvUrl" class="btn btn-outline" target="_blank">View CV</a>
        </div>

        <div class="hero-stats" aria-label="Portfolio highlights">
          <div>
            <strong>10+</strong>
            <span>Core tools</span>
          </div>
          <div>
            <strong>3</strong>
            <span>Live projects</span>
          </div>
          <div>
            <strong>2nd</strong>
            <span>Year student</span>
          </div>
        </div>
      </div>

      <div class="hero-visual">
        <div class="portrait-card">
          <img :src="portraitUrl" alt="Molika Lon portrait">
        </div>
        <div class="floating-roles" aria-label="Main roles">
          <span class="floating-role floating-role-qa">QA</span>
          <span class="floating-role floating-role-frontend">Frontend</span>
          <span class="floating-role floating-role-ux">UX/UI</span>
        </div>
      </div>
    </section>

    <section id="stack" class="tech-section">
      <div class="section-heading centered">
        <p class="eyebrow">Tech Stack</p>
        <h2>Technologies I work with</h2>
      </div>

      <div class="tech-marquee" aria-label="Technology list">
        <div class="tech-track">
          <span v-for="tech in marqueeTech" :key="tech">{{ tech }}</span>
        </div>
      </div>

      <div class="stack-grid">
        <article v-for="skill in stackSkills" :key="skill.name" class="stack-item">
          <div class="stack-header">
            <h3>{{ skill.name }}</h3>
            <span>{{ skill.level }}%</span>
          </div>
          <div class="skill-bar">
            <div class="bar-fill" :style="{ width: `${skill.level}%` }"></div>
          </div>
        </article>
      </div>
    </section>

    <section id="projects" class="projects-section">
      <div class="section-heading">
        <p class="eyebrow">Featured Projects</p>
        <h2>Recent frontend and UX/UI work</h2>
        <p>Some projects that show my growing skills in interface quality, front-end logic, usability, and teamwork.</p>
      </div>

      <div class="projects-grid">
        <article v-for="project in projects" :key="project.title" class="project-card">
          <a
            :class="['project-image', project.imageClass]"
            :href="project.url"
            :title="project.title"
            target="_blank"
          >
            <img :src="project.image" :alt="`${project.title} preview`">
          </a>
          <div class="project-content">
            <span class="project-number">{{ project.number }}</span>
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
            <div class="project-tags">
              <span v-for="tag in project.tags" :key="tag">{{ tag }}</span>
            </div>
          </div>
        </article>
      </div>
    </section>

    <section id="about" class="about-section">
      <div class="about-image">
        <img :src="portraitUrl" alt="Molika Lon">
      </div>
      <div class="about-copy">
        <p class="eyebrow">About Me</p>
        <h2>A curious QA frontend and UX/UI learner improving products by testing and building.</h2>
        <p>
          My name is Molika Lon. I'm {{ age }} years old and currently a second-year student at PNC.
          I enjoy exploring new technologies, solving problems, and creating web applications that feel useful and easy to use.
        </p>
        <p>
          I study frontend development, QA practice, and UX/UI design, and I care about communication, teamwork, time management,
          and steadily improving my craft.
        </p>
      </div>
    </section>

    <section id="skills" class="skills-section">
      <div class="section-heading centered">
        <p class="eyebrow">Skills Overview</p>
        <h2>My technical expertise and soft skills</h2>
      </div>

      <div class="skills-layout">
        <div class="skills-panel">
          <h3>Hard Skills</h3>
          <div class="skills-container">
            <div v-for="skill in hardSkills" :key="skill.name" class="skill-card">
              <img :src="skill.icon" :alt="skill.name">
              <p>{{ skill.name }}</p>
            </div>
          </div>
        </div>

        <div class="skills-panel">
          <h3>Soft Skills</h3>
          <div class="soft-list">
            <span v-for="skill in softSkills" :key="skill">{{ skill }}</span>
          </div>
        </div>
      </div>
    </section>

    <section class="explore-section">
      <div class="section-heading centered">
        <p class="eyebrow">Explore My Portfolio</p>
        <h2>Navigate through my work and expertise</h2>
      </div>
      <div class="explore-grid">
        <a v-for="link in exploreLinks" :key="link.href" :href="link.href">
          {{ link.title }}
          <span>{{ link.description }}</span>
        </a>
      </div>
    </section>

    <section id="contact" class="contact-section">
      <div class="contact-copy">
        <p class="eyebrow">Let's Work Together</p>
        <h2>I'm open to new ideas, practice projects, and collaborations.</h2>
        <p>
          Email me directly at
          <a href="mailto:lonmolika303@gmail.com">lonmolika303@gmail.com</a>
          or send a quick message here.
        </p>
        <div class="social-links">
          <a href="https://github.com/Molika207" target="_blank">GitHub</a>
          <a href="https://www.linkedin.com/in/molika-lon-403811393/" target="_blank">LinkedIn</a>
          <a href="https://www.facebook.com/lon.molika" target="_blank">Facebook</a>
          <a :href="cvUrl" target="_blank">CV</a>
        </div>
      </div>

      <form class="contact-form" novalidate @submit.prevent="submitForm">
        <div class="form-row">
          <label for="name">Name</label>
          <input id="name" v-model.trim="form.name" type="text" required>
        </div>
        <div class="form-row">
          <label for="email">Email</label>
          <input id="email" v-model.trim="form.email" type="email" required>
        </div>
        <div class="form-row">
          <label for="message">Message</label>
          <textarea id="message" v-model.trim="form.message" required></textarea>
        </div>
        <button type="submit" :disabled="submitting">
          {{ submitting ? 'Sending...' : 'Send Message' }}
        </button>
        <p v-if="success" class="success">Message sent.</p>
        <p v-if="error" class="error">{{ error }}</p>
      </form>
    </section>
  </main>

  <footer>
    <p>Developed by Molika Lon</p>
  </footer>
</template>

<script setup>
import { computed, onMounted, onUnmounted, reactive, ref } from 'vue';

import portraitUrl from '../image/image1.png';
import dessertUrl from '../image/dessert.png';
import weatherUrl from '../image/weather.png';
import somaetUrl from '../image/somaet.png';
import htmlIcon from '../image/html.png';
import cssIcon from '../image/css.png';
import jsIcon from '../image/js.png';
import pythonIcon from '../image/python.png';
import figmaIcon from '../image/figma.png';
import githubIcon from '../image/github.png';
import sassIcon from '../image/sass.png';
import vercelIcon from '../image/vercel.png';

const cvUrl = new URL('../cv/Professional CV .pdf', import.meta.url).href;

const form = reactive({
  name: '',
  email: '',
  message: ''
});

const submitting = ref(false);
const success = ref(false);
const error = ref('');
const typedName = ref('');
const fullName = "Hi, I'm\nMolika Lon";
const typeIndex = ref(0);
const deletingName = ref(false);
const birthDate = '2007-03-30';
let typingTimer;

const marqueeTech = [
  'HTML',
  'CSS',
  'JavaScript',
  'Python',
  'Figma',
  'GitHub',
  'Sass',
  'Vercel',
  'Ubuntu',
  'Git',
  'HTML',
  'CSS',
  'JavaScript',
  'Python',
  'Figma',
  'GitHub'
];

const stackSkills = [
  { name: 'Frontend QA', level: 90 },
  { name: 'JavaScript', level: 86 },
  { name: 'UX/UI Design', level: 88 },
  { name: 'Testing Mindset', level: 82 }
];

const projects = [
  {
    number: '01',
    title: 'Dessert E-Commerce',
    description: 'A polished product website for browsing desserts with a clean shopping-style interface.',
    url: 'https://dessert-website-pi.vercel.app/',
    image: dessertUrl,
    imageClass: 'project-icon',
    tags: ['HTML', 'CSS', 'JavaScript']
  },
  {
    number: '02',
    title: 'Weather System',
    description: 'A team project focused on weather data presentation, simple navigation, and useful interface states.',
    url: 'https://weathersystemgroup2.vercel.app/',
    image: weatherUrl,
    imageClass: 'project-icon weather',
    tags: ['API', 'JavaScript', 'Teamwork']
  },
  {
    number: '03',
    title: 'Somaet Website',
    description: 'A live website project with a stronger visual identity and responsive content sections.',
    url: 'https://somaet.website/',
    image: somaetUrl,
    imageClass: '',
    tags: ['Web Design', 'Responsive', 'Vercel']
  }
];

const hardSkills = [
  { name: 'HTML', icon: htmlIcon },
  { name: 'CSS', icon: cssIcon },
  { name: 'JavaScript', icon: jsIcon },
  { name: 'Python', icon: pythonIcon },
  { name: 'Figma', icon: figmaIcon },
  { name: 'GitHub', icon: githubIcon },
  { name: 'Sass', icon: sassIcon },
  { name: 'Vercel', icon: vercelIcon }
];

const softSkills = [
  'Communication',
  'Problem Solving',
  'Adaptability',
  'Responsibility',
  'Teamwork',
  'Time Management',
  'Leadership',
  'Research'
];

const exploreLinks = [
  {
    href: '#about',
    title: 'About Me',
    description: 'Learn about my journey and what drives me.'
  },
  {
    href: '#projects',
    title: 'My Projects',
    description: 'Explore my recent web applications.'
  },
  {
    href: '#skills',
    title: 'Skills & Tech',
    description: 'Discover the tools I use to build.'
  },
  {
    href: '#contact',
    title: 'Get in Touch',
    description: 'Start a conversation or collaboration.'
  }
];

const age = computed(() => {
  const today = new Date();
  const birth = new Date(birthDate);
  let years = today.getFullYear() - birth.getFullYear();
  const birthdayThisYear = new Date(today.getFullYear(), birth.getMonth(), birth.getDate());

  if (today < birthdayThisYear) {
    years -= 1;
  }

  return years;
});

function queueTyping(delay) {
  typingTimer = window.setTimeout(typeHeroName, delay);
}

function typeHeroName() {
  const speed = deletingName.value ? 70 : 115;
  const pause = deletingName.value ? 400 : 1400;

  if (!deletingName.value && typeIndex.value <= fullName.length) {
    typedName.value = fullName.slice(0, typeIndex.value);
    typeIndex.value += 1;
    queueTyping(speed);
    return;
  }

  if (!deletingName.value) {
    deletingName.value = true;
    queueTyping(pause);
    return;
  }

  if (deletingName.value && typeIndex.value >= 0) {
    typedName.value = fullName.slice(0, typeIndex.value);
    typeIndex.value -= 1;
    queueTyping(speed);
    return;
  }

  deletingName.value = false;
  typeIndex.value = 0;
  queueTyping(pause);
}

function submitForm() {
  success.value = false;
  error.value = '';

  if (!form.name || !form.email || !form.message) {
    error.value = 'Please fill out all fields.';
    return;
  }

  submitting.value = true;

  window.setTimeout(() => {
    submitting.value = false;
    success.value = true;
    form.name = '';
    form.email = '';
    form.message = '';
  }, 600);
}

onMounted(() => {
  typeHeroName();
});

onUnmounted(() => {
  window.clearTimeout(typingTimer);
});
</script>
