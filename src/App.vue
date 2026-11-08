<script setup lang="ts">
import { onMounted, ref } from 'vue'
import TheFooter from './components/TheFooter.vue'
import Hero from './components/TheHero.vue'
import TheList from './components/TheList.vue'

type ThemeMode = 'light' | 'dark'

const theme = ref<ThemeMode>('light')

function applyTheme(next: ThemeMode) {
  theme.value = next
  document.documentElement.setAttribute('data-theme', next)
}

function toggleTheme() {
  const next: ThemeMode = theme.value === 'light' ? 'dark' : 'light'
  applyTheme(next)
  try {
    localStorage.setItem('jingji-theme', next)
  } catch {
    // Ignore storage errors
  }
}

onMounted(() => {
  let saved: string | null = null
  try {
    saved = localStorage.getItem('jingji-theme')
  } catch {
    saved = null
  }

  if (saved === 'light' || saved === 'dark') {
    applyTheme(saved)
    return
  }

  const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches
  applyTheme(prefersDark ? 'dark' : 'light')
})
</script>

<template>
  <div class="page-layout">
    <button
      type="button"
      class="theme-switch"
      :aria-label="theme === 'dark' ? '切换为浅色模式' : '切换为深色模式'"
      :title="theme === 'dark' ? '切换为浅色模式' : '切换为深色模式'"
      @click="toggleTheme"
    >
      <svg
        v-if="theme === 'light'"
        xmlns="http://www.w3.org/2000/svg"
        width="18"
        height="18"
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        stroke-width="1.75"
        stroke-linecap="round"
        stroke-linejoin="round"
        aria-hidden="true"
      >
        <circle cx="12" cy="12" r="4" />
        <path d="M12 2v2" />
        <path d="M12 20v2" />
        <path d="m4.93 4.93 1.41 1.41" />
        <path d="m17.66 17.66 1.41 1.41" />
        <path d="M2 12h2" />
        <path d="M20 12h2" />
        <path d="m6.34 17.66-1.41 1.41" />
        <path d="m19.07 4.93-1.41 1.41" />
      </svg>
      <svg
        v-else
        xmlns="http://www.w3.org/2000/svg"
        width="18"
        height="18"
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        stroke-width="1.75"
        stroke-linecap="round"
        stroke-linejoin="round"
        aria-hidden="true"
      >
        <path d="M12 3a6 6 0 0 0 9 9 9 9 0 1 1-9-9Z" />
      </svg>
    </button>

    <div class="content-stage">
      <header class="hero-column">
        <Hero msg="荆棘鸟文学社" :theme="theme" />
      </header>

      <main class="list-column">
        <TheList />
      </main>
    </div>

    <TheFooter />
  </div>
</template>

<style scoped>
.page-layout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  position: relative;
  padding: 0 2rem;
}

.theme-switch {
  position: fixed;
  top: 1.75rem;
  right: 2rem;
  z-index: 10;
  width: 38px;
  height: 38px;
  border-radius: 50%;
  border: 1px solid var(--border-hairline);
  background: transparent;
  color: var(--text-secondary);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition:
    color 0.25s ease,
    border-color 0.25s ease,
    background-color 0.25s ease;
}

.theme-switch:hover {
  color: var(--accent-primary);
  border-color: var(--border-hover);
  background: var(--bg-hover);
}

.content-stage {
  flex: 1;
  width: 100%;
  max-width: 1040px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr;
  align-items: center;
  gap: 3.5rem;
  padding: 5rem 0 3rem;
}

@media (min-width: 900px) {
  .content-stage {
    grid-template-columns: 1fr 1.15fr;
    gap: 5rem;
    padding: 0;
  }

  .hero-column {
    padding-right: 3rem;
    border-right: 1px solid var(--border-hairline);
  }
}

@media (max-width: 640px) {
  .page-layout {
    padding: 0 1.5rem;
  }

  .theme-switch {
    top: 1.25rem;
    right: 1.25rem;
  }

  .content-stage {
    gap: 2.5rem;
    padding: 4.5rem 0 2.5rem;
  }
}
</style>
