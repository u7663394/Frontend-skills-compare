<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue'

type FocusItem = {
  label: string
  text: string
}

type Project = {
  name: string
  type: string
  description: string
  href: string
}

const focusItems: FocusItem[] = [
  {
    label: 'ANU Advanced Computing',
    text: 'Honours study with a machine learning specialisation and practical software engineering focus.',
  },
  {
    label: 'Techlauncher-LeafAnalyzer',
    text: 'Contributing to leaf analysis workflows across pattern generation, AprilTag overlays, and curvature tooling.',
  },
  {
    label: 'Frontend Systems',
    text: 'Building Vue, React, and TypeScript interfaces with attention to clean interaction and polished delivery.',
  },
]

const projects: Project[] = [
  {
    name: 'LGGC liquid glass',
    type: 'Frontend library',
    description: 'A lightweight open-source library for modern liquid glass UI effects.',
    href: 'https://github.com/u7663394/LGGC-liquid-glass',
  },
  {
    name: 'consult-patient-vue3-ts',
    type: 'Vue 3 + TypeScript',
    description: 'A mobile frontend application for patient consultation workflows.',
    href: 'https://github.com/u7663394/consult-patient-vue3-ts',
  },
  {
    name: 'CNN Canny Edge Predictor',
    type: 'Computer vision',
    description: 'A Mini-U-Net experiment that predicts Canny-style edge locations from augmented image patches.',
    href: 'https://github.com/u7663394/CNN-Canny-Edge-Predictor',
  },
  {
    name: 'react-learning-journey',
    type: 'Learning in public',
    description: 'Notes, demos, and implementation experiments from an ongoing React learning process.',
    href: 'https://github.com/u7663394/react-learning-journey',
  },
]

const profileUrl = 'https://github.com/u7663394'
const avatarUrl = 'https://github.com/u7663394.png'
const scrollProgress = ref(0)
const pointerX = ref(0)
const pointerY = ref(0)
let revealObserver: IntersectionObserver | undefined

const updateScrollProgress = () => {
  const scrollable = document.documentElement.scrollHeight - window.innerHeight
  scrollProgress.value = scrollable > 0 ? window.scrollY / scrollable : 0
}

const updatePointer = (event: PointerEvent) => {
  pointerX.value = (event.clientX / window.innerWidth - 0.5) * 2
  pointerY.value = (event.clientY / window.innerHeight - 0.5) * 2
}

onMounted(() => {
  updateScrollProgress()
  window.addEventListener('scroll', updateScrollProgress, { passive: true })
  window.addEventListener('pointermove', updatePointer, { passive: true })

  const revealTargets = document.querySelectorAll<HTMLElement>('[data-reveal]')
  revealObserver = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('is-visible')
          revealObserver?.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.24 },
  )

  revealTargets.forEach((target) => revealObserver?.observe(target))
})

onBeforeUnmount(() => {
  revealObserver?.disconnect()
  window.removeEventListener('scroll', updateScrollProgress)
  window.removeEventListener('pointermove', updatePointer)
})
</script>

<template>
  <main
    class="site-shell"
    :style="{
      '--scroll-progress': scrollProgress.toString(),
      '--pointer-x': pointerX.toString(),
      '--pointer-y': pointerY.toString(),
    }"
  >
    <div class="progress-line" aria-hidden="true"></div>

    <header class="topbar" aria-label="Primary navigation">
      <a class="wordmark" href="#top" aria-label="Guochen Wang home">Guochen Wang</a>
      <nav class="nav-links">
        <a href="#focus">Focus</a>
        <a href="#work">Work</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <section id="top" class="hero" aria-labelledby="hero-title">
      <div class="hero-visual" aria-hidden="true">
        <div class="leaf-field">
          <span v-for="index in 7" :key="index"></span>
        </div>
        <img class="avatar-plane" :src="avatarUrl" alt="" />
      </div>

      <div class="hero-copy">
        <p class="eyebrow">u7663394 · Australia · ANU</p>
        <h1 id="hero-title">Guochen Wang</h1>
        <p class="hero-line">
          Advanced Computing student turning machine learning, computer vision, and frontend craft into usable web tools.
        </p>
        <div class="hero-actions" aria-label="Profile actions">
          <a class="primary-link" :href="profileUrl" target="_blank" rel="noreferrer">View GitHub</a>
          <a class="text-link" href="mailto:guochenwang710@gmail.com">Email</a>
        </div>
      </div>

      <div class="hero-caption" aria-label="Current profile snapshot">
        <span>Vue 3</span>
        <span>TypeScript</span>
        <span>ML/CV</span>
      </div>
    </section>

    <section id="focus" class="focus-section" data-reveal aria-labelledby="focus-title">
      <div class="section-kicker">Current Focus</div>
      <h2 id="focus-title">Building where interface clarity meets image intelligence.</h2>
      <div class="focus-list">
        <article v-for="item in focusItems" :key="item.label" class="focus-row">
          <h3>{{ item.label }}</h3>
          <p>{{ item.text }}</p>
        </article>
      </div>
    </section>

    <section class="leaf-story" data-reveal aria-labelledby="leaf-title">
      <div class="story-pin">
        <p class="section-kicker">Techlauncher-LeafAnalyzer</p>
        <h2 id="leaf-title">From leaf patterns to practical tooling.</h2>
      </div>
      <div class="story-lines" aria-label="LeafAnalyzer contribution areas">
        <p>Pattern generation for visual analysis workflows.</p>
        <p>AprilTag overlay tools for image output inspection.</p>
        <p>Curvature experiments connecting ML models with plant morphology.</p>
      </div>
    </section>

    <section id="work" class="work-section" data-reveal aria-labelledby="work-title">
      <div class="work-heading">
        <p class="section-kicker">Selected Work</p>
        <h2 id="work-title">Projects that show the range.</h2>
      </div>

      <div class="project-rail">
        <a v-for="project in projects" :key="project.name" class="project-row" :href="project.href" target="_blank" rel="noreferrer">
          <span class="project-type">{{ project.type }}</span>
          <strong>{{ project.name }}</strong>
          <span class="project-description">{{ project.description }}</span>
        </a>
      </div>
    </section>

    <section id="contact" class="contact-section" data-reveal aria-labelledby="contact-title">
      <p class="section-kicker">Open Profile</p>
      <h2 id="contact-title">Follow the experiments, notes, and build logs on GitHub.</h2>
      <a class="primary-link" :href="profileUrl" target="_blank" rel="noreferrer">Open @u7663394</a>
    </section>
  </main>
</template>
