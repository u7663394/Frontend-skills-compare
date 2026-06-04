<script setup lang="ts">
import {
  PhArrowUpRight,
  PhBrain,
  PhCode,
  PhEnvelopeSimple,
  PhGithubLogo,
  PhGraduationCap,
  PhLeaf,
  PhSparkle,
} from "@phosphor-icons/vue";
import heroWorkspace from "./assets/hero-workspace.jpg";

type Project = {
  name: string;
  role: string;
  description: string;
  stack: string;
  href: string;
  image: string;
};

type Focus = {
  title: string;
  body: string;
};

const focuses: Focus[] = [
  {
    title: "Frontend systems",
    body: "Building Vue, React, and TypeScript applications with attention to interaction, polish, and maintainable UI structure.",
  },
  {
    title: "Machine learning",
    body: "Exploring computer vision models, contrastive learning, image analysis, and practical workflows for visual data.",
  },
  {
    title: "Learning in public",
    body: "Keeping notes, demos, and experiments visible through small repositories and hands-on project work.",
  },
];

const projects: Project[] = [
  {
    name: "LGGC-liquid-glass",
    role: "Frontend library",
    description: "A lightweight library for liquid glass UI effects with a modern, simple, open-source direction.",
    stack: "HTML, CSS, JavaScript",
    href: "https://github.com/u7663394/LGGC-liquid-glass",
    image: "https://picsum.photos/seed/liquid-glass-interface/960/720",
  },
  {
    name: "consult-patient-vue3-ts",
    role: "Vue 3 mobile app",
    description: "A Vue 3 and TypeScript frontend application for patient consultation workflows.",
    stack: "Vue, TypeScript",
    href: "https://github.com/u7663394/consult-patient-vue3-ts",
    image: "https://picsum.photos/seed/vue-mobile-consultation/960/720",
  },
  {
    name: "CNN-Canny-Edge-Predictor",
    role: "Computer vision",
    description: "A CNN experiment that predicts Canny edge locations using a lightweight Mini-U-Net approach.",
    stack: "Python, CNN",
    href: "https://github.com/u7663394/CNN-Canny-Edge-Predictor",
    image: "https://picsum.photos/seed/cnn-edge-prediction-leaf/960/720",
  },
];

const toolGroups = [
  ["Vue 3", "React", "TypeScript", "Vite"],
  ["Python", "CNN", "SimCLR", "Computer Vision"],
  ["GitHub", "ANU TechLauncher", "UI polish", "Open source"],
];
</script>

<template>
  <main class="page-shell">
    <header class="site-nav" aria-label="Primary navigation">
      <a class="brand-lockup" href="#top" aria-label="Guochen Wang homepage">
        <img src="https://github.com/u7663394.png?size=96" alt="Guochen Wang GitHub avatar" />
        <span>Guochen Wang</span>
      </a>
      <nav>
        <a href="#work">Work</a>
        <a href="#focus">Focus</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <section id="top" class="hero-section">
      <div class="hero-copy reveal">
        <p class="eyebrow">ANU Advanced Computing</p>
        <h1>Frontend craft with machine learning curiosity.</h1>
        <p class="hero-lede">
          I build polished Vue and TypeScript interfaces while exploring applied computer vision.
        </p>
        <div class="hero-actions" aria-label="Primary links">
          <a class="button primary" href="https://github.com/u7663394" target="_blank" rel="noreferrer">
            <PhGithubLogo :size="19" weight="duotone" />
            GitHub
          </a>
          <a class="button secondary" href="mailto:guochenwang710@gmail.com">
            <PhEnvelopeSimple :size="19" weight="duotone" />
            Email
          </a>
        </div>
      </div>

      <div class="hero-visual reveal delay-1" aria-label="Developer workspace visual">
        <img
          :src="heroWorkspace"
          alt="Abstract workspace image representing leaf analysis and frontend experiments"
        />
        <div class="visual-panel">
          <span>Current work</span>
          <strong>LeafAnalyzer, Vue apps, and CV experiments</strong>
        </div>
      </div>
    </section>

    <section id="focus" class="focus-section">
      <div class="section-intro reveal">
        <h2>A practical mix of interface work and applied ML.</h2>
        <p>
          The GitHub profile points to a clear direction: keep shipping frontend projects, study machine
          learning deeply, and connect both through image-analysis tools.
        </p>
      </div>

      <div class="focus-grid" aria-label="Focus areas">
        <article v-for="(focus, index) in focuses" :key="focus.title" class="focus-card reveal" :class="`delay-${index}`">
          <component :is="[PhCode, PhBrain, PhSparkle][index]" :size="28" weight="duotone" aria-hidden="true" />
          <h3>{{ focus.title }}</h3>
          <p>{{ focus.body }}</p>
        </article>
      </div>
    </section>

    <section class="leaf-section">
      <div class="leaf-visual reveal">
        <img
          src="https://picsum.photos/seed/techlauncher-leaf-analyzer/1100/880"
          alt="Close detail of leaves, used as a visual cue for LeafAnalyzer work"
        />
      </div>
      <div class="leaf-copy reveal delay-1">
        <PhLeaf :size="42" weight="duotone" aria-hidden="true" />
        <h2>Contributing through TechLauncher LeafAnalyzer.</h2>
        <p>
          Guochen participates in current LeafAnalyzer projects, including pattern generation, AprilTag
          overlays, and curvature analysis.
        </p>
        <a class="text-link" href="https://github.com/Techlauncher-LeafAnalyzer" target="_blank" rel="noreferrer">
          View organization
          <PhArrowUpRight :size="18" weight="bold" />
        </a>
      </div>
    </section>

    <section id="work" class="work-section">
      <div class="section-intro reveal">
        <h2>Selected repositories with a working theme.</h2>
        <p>Frontend libraries, Vue applications, and computer vision experiments form the current portfolio spine.</p>
      </div>

      <div class="project-grid">
        <article v-for="project in projects" :key="project.name" class="project-card reveal">
          <img :src="project.image" :alt="`${project.name} representative image`" />
          <div>
            <span>{{ project.role }}</span>
            <h3>{{ project.name }}</h3>
            <p>{{ project.description }}</p>
            <div class="project-meta">
              <small>{{ project.stack }}</small>
              <a :href="project.href" target="_blank" rel="noreferrer" :aria-label="`Open ${project.name} on GitHub`">
                <PhArrowUpRight :size="18" weight="bold" />
              </a>
            </div>
          </div>
        </article>
      </div>
    </section>

    <section class="tool-section">
      <div class="tool-copy reveal">
        <PhGraduationCap :size="38" weight="duotone" aria-hidden="true" />
        <h2>Studying advanced computing with a machine learning specialisation.</h2>
        <p>
          Academic work at ANU anchors the technical depth, while side projects keep the learning practical
          and visible.
        </p>
      </div>

      <div class="tool-cloud" aria-label="Technology stack">
        <div v-for="group in toolGroups" :key="group.join('-')" class="tool-row reveal">
          <span v-for="tool in group" :key="tool">{{ tool }}</span>
        </div>
      </div>
    </section>

    <footer id="contact" class="footer-section">
      <div>
        <h2>Open to practical frontend and ML conversations.</h2>
        <p>Best reached through GitHub or email.</p>
      </div>
      <div class="footer-actions">
        <a class="button primary" href="mailto:guochenwang710@gmail.com">
          <PhEnvelopeSimple :size="19" weight="duotone" />
          Email
        </a>
        <a class="button secondary" href="https://github.com/u7663394" target="_blank" rel="noreferrer">
          <PhGithubLogo :size="19" weight="duotone" />
          GitHub
        </a>
      </div>
    </footer>
  </main>
</template>
