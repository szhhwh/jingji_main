<script setup lang="ts">
import logoUrl from '@/assets/logo.svg'
import logoDarkUrl from '@/assets/logo-dark.svg'

defineProps<{
  msg: string
  theme: 'light' | 'dark'
}>()
</script>

<template>
  <div class="hero">
    <img :src="theme === 'dark' ? logoDarkUrl : logoUrl" alt="荆棘鸟文学社标志" class="logo" width="112" height="112" />

    <div class="greetings">
      <h1 class="title">{{ msg }}</h1>
      <div class="accent-rule" aria-hidden="true"></div>
      <p class="subtitle">欢迎来到荆棘鸟文学社官网</p>
    </div>
  </div>
</template>

<style scoped>
.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 1.75rem;
}

.logo {
  width: 112px;
  height: 112px;
  object-fit: contain;
}

.greetings {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.9rem;
}

.title {
  font-family: var(--font-serif);
  font-size: clamp(2.1rem, 3.5vw, 2.75rem);
  font-weight: 700;
  letter-spacing: 0.16em;
  line-height: 1.25;
  color: var(--text-primary);
}

.accent-rule {
  width: 72px;
  height: 2px;
  background: var(--accent-line);
  border-radius: 2px;
}

.subtitle {
  font-size: 1.05rem;
  color: var(--text-secondary);
  letter-spacing: 0.04em;
}

@media (min-width: 900px) {
  .hero {
    align-items: flex-start;
    text-align: left;
  }

  .greetings {
    align-items: flex-start;
  }
}
</style>
