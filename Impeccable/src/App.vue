<script setup lang="ts">
type Project = {
  title: string
  summary: string
  meta: string
  href: string
}

type FocusItem = {
  label: string
  detail: string
}

const projects: Project[] = [
  {
    title: 'Techlauncher-LeafAnalyzer',
    summary:
      'Capstone work across pattern generation, AprilTag overlays, and leaf curvature analysis for a plant-image workflow.',
    meta: 'ANU TechLauncher, CV workflow',
    href: 'https://github.com/Techlauncher-LeafAnalyzer',
  },
  {
    title: 'LGGC-liquid-glass',
    summary:
      'A lightweight frontend library exploring liquid glass interface effects and Vue-friendly visual materials.',
    meta: 'Frontend library',
    href: 'https://github.com/u7663394/LGGC-liquid-glass',
  },
  {
    title: 'CNN-Canny-Edge-Predictor',
    summary:
      'Mini U-Net experiment that predicts Canny edge locations from augmented image patches.',
    meta: 'Python, PyTorch, image analysis',
    href: 'https://github.com/u7663394/CNN-Canny-Edge-Predictor',
  },
  {
    title: 'react-learning-journey',
    summary:
      'Notes, demos, and small experiments documenting React practice alongside Vue and TypeScript work.',
    meta: 'Learning in public',
    href: 'https://github.com/u7663394/react-learning-journey',
  },
]

const focusItems: FocusItem[] = [
  {
    label: 'Machine learning',
    detail: 'Applied model experiments, contrastive learning, CNNs, and practical computer vision workflows.',
  },
  {
    label: 'Frontend systems',
    detail: 'Vue 3, React, TypeScript, application tooling, and interface details that stay understandable.',
  },
  {
    label: 'Research habits',
    detail: 'Small repos, visible notes, and prototypes that turn coursework and curiosity into public artifacts.',
  },
]

const stack = [
  'Vue',
  'React',
  'TypeScript',
  'Vite',
  'Pinia',
  'Python',
  'PyTorch',
  'OpenCV',
  'Docker',
  'Git',
]
</script>

<template>
  <main class="page-shell">
    <section class="hero" aria-labelledby="hero-title">
      <div class="hero__content">
        <p class="kicker">Australia · ANU Advanced Computing (Honours)</p>
        <h1 id="hero-title">
          <span>Guochen</span>
          <span>Wang</span>
          <span>builds AI and</span>
          <span>vision</span>
          <span>interfaces.</span>
        </h1>
        <p class="hero__intro">
          I am an ANU computing student with a machine learning specialisation, exploring AI,
          computer vision, and polished Vue, React, and TypeScript interfaces.
        </p>
        <div class="hero__actions" aria-label="Primary links">
          <a class="button button--primary" href="https://github.com/u7663394" target="_blank" rel="noreferrer">
            View GitHub profile
          </a>
          <a class="button button--secondary" href="mailto:guochenwang710@gmail.com">
            Email Guochen
          </a>
        </div>
      </div>

      <aside class="hero-card" aria-label="Profile summary">
        <div class="portrait-wrap">
          <img
            class="portrait"
            src="https://avatars.githubusercontent.com/u/126779461?v=4"
            alt="GitHub avatar for Guochen Wang"
          />
          <div class="scan-ring" aria-hidden="true"></div>
        </div>
        <div>
          <p class="hero-card__name">u7663394</p>
          <p class="hero-card__role">AI, CV, and frontend learner</p>
        </div>
        <dl class="signal-list">
          <div>
            <dt>Public repos</dt>
            <dd>15</dd>
          </div>
          <div>
            <dt>Profile focus</dt>
            <dd>Leaf analysis · liquid glass · learning notes</dd>
          </div>
          <div>
            <dt>Current base</dt>
            <dd>Australia</dd>
          </div>
        </dl>
      </aside>
    </section>

    <section class="vision-band" aria-label="Machine vision sketch">
      <div class="vision-copy">
        <h2>Current work is shaped by image analysis and usable interfaces.</h2>
        <p>
          The public profile points to leaf analysis tooling, AprilTag overlays, CNN edge
          prediction, and hands-on frontend libraries. This page treats those as one story:
          seeing patterns clearly, then making them workable.
        </p>
      </div>
      <div class="vision-panel" aria-hidden="true">
        <span class="node node--a"></span>
        <span class="node node--b"></span>
        <span class="node node--c"></span>
        <span class="node node--d"></span>
        <span class="vision-line vision-line--one"></span>
        <span class="vision-line vision-line--two"></span>
        <span class="vision-line vision-line--three"></span>
        <span class="scan-beam"></span>
      </div>
    </section>

    <section class="focus-section" aria-labelledby="focus-title">
      <div class="section-heading">
        <p class="section-label">Focus</p>
        <h2 id="focus-title">A compact practice across models, interfaces, and evidence.</h2>
      </div>
      <div class="focus-list">
        <article v-for="item in focusItems" :key="item.label" class="focus-item">
          <h3>{{ item.label }}</h3>
          <p>{{ item.detail }}</p>
        </article>
      </div>
    </section>

    <section class="projects-section" aria-labelledby="projects-title">
      <div class="section-heading section-heading--wide">
        <p class="section-label">Selected work</p>
        <h2 id="projects-title">Projects with a visible learning trail.</h2>
        <p>
          These are drawn from the public GitHub profile and rewritten as portfolio signals,
          not repository badges.
        </p>
      </div>

      <div class="project-list">
        <a v-for="project in projects" :key="project.title" class="project-row" :href="project.href" target="_blank" rel="noreferrer">
          <span class="project-row__meta">{{ project.meta }}</span>
          <span class="project-row__title">{{ project.title }}</span>
          <span class="project-row__summary">{{ project.summary }}</span>
        </a>
      </div>
    </section>

    <section class="stack-section" aria-labelledby="stack-title">
      <div>
        <p class="section-label">Stack</p>
        <h2 id="stack-title">Tools that support the loop.</h2>
      </div>
      <ul class="stack-list" aria-label="Technology stack">
        <li v-for="item in stack" :key="item">{{ item }}</li>
      </ul>
    </section>
  </main>
</template>
