<script setup lang="ts">
import {
  ArrowUpRight,
  BookOpenCheck,
  BrainCircuit,
  Code2,
  Github,
  GraduationCap,
  Leaf,
  Mail,
  MapPin,
  Moon,
  Settings2,
  Sun,
} from 'lucide-vue-next';
import { computed, ref } from 'vue';
import avatarUrl from './assets/guochen-avatar.png';
import labVisualUrl from './assets/leaf-analysis-lab.svg';

type Tone = 'paper' | 'midnight';

interface Project {
  name: string;
  label: string;
  description: string;
  tech: string;
  href: string;
}

interface FocusItem {
  title: string;
  detail: string;
}

const tone = ref<Tone>('paper');
const showTweaks = ref(false);

const pageClass = computed(() => ({
  'theme-midnight': tone.value === 'midnight',
}));

const focusItems: FocusItem[] = [
  {
    title: 'Advanced computing at ANU',
    detail:
      'Honours student building a foundation across machine learning, software engineering, and frontend systems.',
  },
  {
    title: 'Applied ML and computer vision',
    detail:
      'Exploring contrastive learning, image analysis workflows, CNN experiments, and practical model iteration.',
  },
  {
    title: 'Frontend craft',
    detail:
      'Building Vue, React, and TypeScript applications with attention to clean interfaces and polished product feel.',
  },
];

const projects: Project[] = [
  {
    name: 'LGGC liquid glass',
    label: 'Frontend library',
    description:
      'A lightweight UI effect library focused on modern liquid-glass treatments for web interfaces.',
    tech: 'HTML',
    href: 'https://github.com/u7663394/LGGC-liquid-glass',
  },
  {
    name: 'Consult patient Vue 3 TS',
    label: 'Mobile web app',
    description:
      'A Vue 3 and TypeScript frontend application for patient consultation workflows.',
    tech: 'Vue',
    href: 'https://github.com/u7663394/consult-patient-vue3-ts',
  },
  {
    name: 'CNN Canny Edge Predictor',
    label: 'Computer vision',
    description:
      'A compact CNN experiment that predicts Canny edge locations using a Mini U-Net style model.',
    tech: 'Python',
    href: 'https://github.com/u7663394/CNN-Canny-Edge-Predictor',
  },
  {
    name: 'React learning journey',
    label: 'Learning in public',
    description:
      'Notes, demos, and experiments from a visible React learning process.',
    tech: 'React',
    href: 'https://github.com/u7663394/react-learning-journey',
  },
];

const stackGroups = [
  {
    title: 'Frontend',
    items: ['Vue 3', 'React', 'TypeScript', 'CSS systems'],
  },
  {
    title: 'ML and CV',
    items: ['Computer vision', 'CNNs', 'SimCLR', 'Image analysis'],
  },
  {
    title: 'Workflow',
    items: ['GitHub', 'Vite', 'Open-source notes', 'Hands-on demos'],
  },
];
</script>

<template>
  <main :class="pageClass" class="site-shell">
    <section class="hero" aria-labelledby="intro-title">
      <nav class="topbar" aria-label="Primary navigation">
        <a class="brand-mark" href="#top" aria-label="Guochen Wang homepage">
          <span class="brand-symbol">GW</span>
          <span>Guochen Wang</span>
        </a>

        <div class="nav-links">
          <a href="#work">Work</a>
          <a href="#focus">Focus</a>
          <a href="#contact">Contact</a>
        </div>
      </nav>

      <div id="top" class="hero-grid">
        <div class="hero-copy">
          <p class="eyebrow">ANU Advanced Computing Honours · Australia</p>
          <h1 id="intro-title">Frontend engineer shaped by machine learning.</h1>
          <p class="hero-lede">
            I am Guochen Wang, also known as
            <code>u7663394</code>. I build Vue, React, and TypeScript interfaces
            while studying machine learning and computer vision at ANU.
          </p>

          <div class="hero-actions" aria-label="Profile actions">
            <a class="button primary" href="https://github.com/u7663394" target="_blank" rel="noreferrer">
              <Github :size="18" aria-hidden="true" />
              GitHub
            </a>
            <a class="button secondary" href="mailto:guochenwang710@gmail.com">
              <Mail :size="18" aria-hidden="true" />
              Email
            </a>
          </div>

          <dl class="signal-row" aria-label="Profile highlights">
            <div>
              <dt>Base</dt>
              <dd><MapPin :size="16" aria-hidden="true" /> Australia</dd>
            </div>
            <div>
              <dt>Specialisation</dt>
              <dd><BrainCircuit :size="16" aria-hidden="true" /> Machine Learning</dd>
            </div>
            <div>
              <dt>Current team</dt>
              <dd><Leaf :size="16" aria-hidden="true" /> Techlauncher-LeafAnalyzer</dd>
            </div>
          </dl>
        </div>

        <aside class="hero-visual" aria-label="Profile visual">
          <img class="lab-visual" :src="labVisualUrl" alt="Leaf analysis workspace illustration" />
          <div class="portrait-card">
            <img class="avatar" :src="avatarUrl" alt="Guochen Wang GitHub avatar" />
            <div>
              <p>Now building</p>
              <strong>Leaf analysis tools and liquid-glass UI experiments</strong>
            </div>
          </div>
        </aside>
      </div>
    </section>

    <section id="focus" class="section-grid focus-section" aria-labelledby="focus-title">
      <div class="section-kicker">
        <GraduationCap :size="22" aria-hidden="true" />
        <span>About</span>
      </div>
      <div>
        <h2 id="focus-title">A bridge between interface craft and visual intelligence.</h2>
        <p class="section-intro">
          The profile centers on learning in public: small repositories, demos,
          experiments, and practical contributions across frontend tooling and
          image-analysis workflows.
        </p>
        <div class="focus-list">
          <article v-for="item in focusItems" :key="item.title" class="focus-item">
            <h3>{{ item.title }}</h3>
            <p>{{ item.detail }}</p>
          </article>
        </div>
      </div>
    </section>

    <section class="leaf-band" aria-labelledby="leaf-title">
      <div>
        <p class="eyebrow">Techlauncher-LeafAnalyzer</p>
        <h2 id="leaf-title">Contributing across the leaf analysis workflow.</h2>
      </div>
      <p>
        Current work includes pattern generation, AprilTag overlay tooling, and
        leaf curvature analysis, connecting frontend interfaces with computer
        vision research needs.
      </p>
      <a class="inline-link" href="https://github.com/Techlauncher-LeafAnalyzer" target="_blank" rel="noreferrer">
        View organization
        <ArrowUpRight :size="17" aria-hidden="true" />
      </a>
    </section>

    <section id="work" class="work-section" aria-labelledby="work-title">
      <div class="section-heading">
        <div>
          <p class="eyebrow">Selected work</p>
          <h2 id="work-title">Projects that show the current direction.</h2>
        </div>
        <a class="inline-link" href="https://github.com/u7663394?tab=repositories" target="_blank" rel="noreferrer">
          All repositories
          <ArrowUpRight :size="17" aria-hidden="true" />
        </a>
      </div>

      <div class="project-grid">
        <article v-for="project in projects" :key="project.name" class="project-card">
          <div class="project-topline">
            <span>{{ project.label }}</span>
            <span>{{ project.tech }}</span>
          </div>
          <h3>{{ project.name }}</h3>
          <p>{{ project.description }}</p>
          <a :href="project.href" target="_blank" rel="noreferrer">
            Open project
            <ArrowUpRight :size="16" aria-hidden="true" />
          </a>
        </article>
      </div>
    </section>

    <section class="stack-section" aria-labelledby="stack-title">
      <div>
        <p class="eyebrow">Stack</p>
        <h2 id="stack-title">Tools with a product-minded edge.</h2>
      </div>
      <div class="stack-columns">
        <article v-for="group in stackGroups" :key="group.title">
          <div class="stack-icon">
            <Code2 v-if="group.title === 'Frontend'" :size="20" aria-hidden="true" />
            <BrainCircuit v-else-if="group.title === 'ML and CV'" :size="20" aria-hidden="true" />
            <BookOpenCheck v-else :size="20" aria-hidden="true" />
          </div>
          <h3>{{ group.title }}</h3>
          <ul>
            <li v-for="item in group.items" :key="item">{{ item }}</li>
          </ul>
        </article>
      </div>
    </section>

    <footer id="contact" class="footer">
      <div>
        <p class="eyebrow">Contact</p>
        <h2>Build, test, learn, publish.</h2>
      </div>
      <div class="footer-actions">
        <a class="button primary" href="mailto:guochenwang710@gmail.com">
          <Mail :size="18" aria-hidden="true" />
          guochenwang710@gmail.com
        </a>
        <a class="button secondary" href="https://github.com/u7663394" target="_blank" rel="noreferrer">
          <Github :size="18" aria-hidden="true" />
          u7663394
        </a>
      </div>
    </footer>

    <button
      class="tweaks-toggle"
      type="button"
      aria-label="Open display settings"
      :aria-expanded="showTweaks"
      @click="showTweaks = !showTweaks"
    >
      <Settings2 :size="18" aria-hidden="true" />
    </button>

    <aside v-if="showTweaks" class="tweaks-panel" aria-label="Tweaks">
      <div class="tweaks-heading">
        <strong>Tweaks</strong>
        <button type="button" aria-label="Close tweaks" @click="showTweaks = false">Close</button>
      </div>
      <div class="segmented" role="group" aria-label="Theme">
        <button
          type="button"
          :class="{ active: tone === 'paper' }"
          @click="tone = 'paper'"
        >
          <Sun :size="16" aria-hidden="true" />
          Paper
        </button>
        <button
          type="button"
          :class="{ active: tone === 'midnight' }"
          @click="tone = 'midnight'"
        >
          <Moon :size="16" aria-hidden="true" />
          Midnight
        </button>
      </div>
    </aside>
  </main>
</template>
