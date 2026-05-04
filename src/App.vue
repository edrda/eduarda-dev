<script setup lang="ts">
import { Icon } from "@iconify/vue";
import { projects } from "./data/projects";
</script>

<template>
  <main class="min-h-screen px-4 py-10">
    <section class="flex justify-center mb-20">
      <div
        class="w-full max-w-5xl p-8 rounded-2xl relative bg-white/5 backdrop-blur-2xl border border-white/10 rounded-2xl shadow-[0_8px_32px_rgba(0,0,0,0.4)] before:absolute before:inset-0 before:rounded-2xl before:bg-gradient-to-br before:from-white/20 before:to-transparent before:opacity-30 before:pointer-events-none"
      >
        <div class="grid md:grid-cols-[240px_1fr] gap-6 items-center">
          <div class="flex justify-center md:justify-start">
            <img
              src="./assets/images/avatar.png"
              class="w-50 h-50 rounded-full border border-white/20 object-cover"
            />
          </div>

          <div class="text-left">
            <h1 class="text-2xl font-semibold mb-2">Eduarda Lourenço</h1>

            <p class="text-sm text-white/70 mb-5 max-w-xl">
              Desenvolvedora front-end com mais de 4 anos de experiência, graduada em Sistemas de Informação. Foco em interfaces modernas, acessibilidade e experiência do usuário.
            </p>

            <div class="flex flex-wrap gap-3">
              <a
                href="https://www.linkedin.com/in/eduarda-lourenco/"
                target="_blank"
                class="flex items-center gap-2 px-4 py-2 rounded-lg flex items-center gap-2 px-4 py-2 rounded-lg bg-white/5 border border-white/10 backdrop-blur-xl hover:bg-white/10 hover:border-white/20 transition active:scale-95"
              >
                <Icon icon="simple-icons:linkedin" class="text-sm" />
                LinkedIn
              </a>

              <a
                href="https://github.com/edrda"
                target="_blank"
                class="flex items-center gap-2 px-4 py-2 rounded-lg flex items-center gap-2 px-4 py-2 rounded-lg bg-white/5 border border-white/10 backdrop-blur-xl hover:bg-white/10 hover:border-white/20 transition active:scale-95"
              >
                <Icon icon="simple-icons:github" class="text-sm" />
                GitHub
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="max-w-5xl mx-auto mb-16">
      <h2 class="text-lg mb-6 text-white/80">Projetos</h2>

      <div
        class="flex gap-4 overflow-x-auto pb-2 snap-x snap-mandatory md:grid md:grid-cols-3 md:gap-6 md:overflow-visible"
      >
        <div
          v-for="project in projects"
          :key="project.title"
          class="group relative min-w-[85%] sm:min-w-[60%] md:min-w-0 bg-white/5 backdrop-blur-2xl border border-white/10 rounded-2xl p-4 transition duration-300 hover:scale-[1.03] hover:shadow-[0_12px_40px_rgba(0,0,0,0.6)] before:absolute before:inset-0 before:rounded-2xl before:bg-gradient-to-br before:from-white/20 before:to-transparent before:opacity-20 before:pointer-events-none snap-start"
        >
          <img
            :src="project.image"
            class="rounded-lg mb-3 w-full h-40 object-cover"
          />

          <h3 class="font-medium">
            {{ project.title }}
          </h3>

          <p class="text-sm text-white/70 mb-4">
            {{ project.description }}
          </p>

          <div class="flex flex-wrap gap-2 mb-4">
            <span
              v-for="tech in project.tech"
              :key="tech"
              class="text-xs px-2 py-1 rounded-md bg-white/10 border border-white/10"
            >
              {{ tech }}
            </span>
          </div>

          <div class="flex gap-2">
            <a
              :href="project.github"
              target="_blank"
              class="flex-1 text-center text-xs py-2 rounded-md border border-white/20 hover:bg-white/20 transition"
            >
              Code
            </a>

            <a
              :href="project.live"
              target="_blank"
              class="flex-1 text-center text-xs py-2 rounded-md bg-[var(--terracotta)] text-white font-medium hover:opacity-90 transition"
            >
              Live
            </a>
          </div>
        </div>
      </div>
    </section>

    <section class="text-center">
      <p class="mb-4 text-white/70">Let's work together</p>

      <div class="flex justify-center gap-3 flex-wrap">
        <a
          href="mailto:edrda.dev@gmail.com"
          class="flex items-center gap-2 px-4 py-2 rounded-lg bg-[var(--terracotta)] text-white font-medium hover:opacity-90 transition"
        >
          <Icon icon="simple-icons:gmail" class="text-sm" />
          Entre em contato
        </a>

        <a
          href="https://drive.google.com/file/d/1JMWer0IvhjjK5o7bB-54X_rrylHZl38X/view?usp=sharing"
          target="_blank"
          class="px-4 py-2 rounded-lg border border-white/20 flex items-center gap-2 px-4 py-2 rounded-lg bg-white/5 border border-white/10 backdrop-blur-xl hover:bg-white/10 hover:border-white/20 transition active:scale-95"
        >
          <Icon icon="heroicons-outline:external-link" class="text-sm" />
          Confira meu currículo
        </a>
      </div>
    </section>
  </main>
</template>
