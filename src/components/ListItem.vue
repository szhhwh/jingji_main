<script setup lang="ts">
defineProps<{
  href: string
}>()
</script>

<template>
  <a :href="href" class="nav-item" rel="noopener">
    <span class="item-icon">
      <slot name="icon"></slot>
    </span>

    <div class="item-content">
      <h2 class="item-title">
        <slot name="heading"></slot>
      </h2>
      <p class="item-desc">
        <slot></slot>
      </p>
    </div>

    <span class="item-arrow" aria-hidden="true">→</span>
  </a>
</template>

<style scoped>
.nav-item {
  display: flex;
  align-items: flex-start;
  gap: 1.25rem;
  padding: 1.75rem 0.75rem;
  border-bottom: 1px solid var(--border-hairline);
  transition: border-color 0.25s ease;
}

.nav-item:first-of-type {
  border-top: 1px solid var(--border-hairline);
}

.nav-item:hover {
  border-bottom-color: var(--border-hover);
}

.item-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 28px;
  height: 28px;
  margin-top: 0.15rem;
  color: var(--accent-primary);
  flex-shrink: 0;
  transition: transform 0.25s ease;
}

.nav-item:hover .item-icon {
  transform: translateY(-1px);
}

.item-content {
  flex: 1;
  min-width: 0;
}

.item-title {
  font-family: var(--font-serif);
  font-size: 1.3rem;
  font-weight: 600;
  letter-spacing: 0.03em;
  color: var(--text-primary);
  margin-bottom: 0.35rem;
  transition: color 0.25s ease;
}

.nav-item:hover .item-title {
  color: var(--accent-primary);
}

.item-desc {
  font-size: 0.95rem;
  color: var(--text-secondary);
  line-height: 1.6;
}

.item-arrow {
  align-self: center;
  font-size: 1.15rem;
  color: var(--text-muted);
  transition:
    transform 0.25s ease,
    color 0.25s ease;
}

.nav-item:hover .item-arrow {
  color: var(--accent-primary);
  transform: translateX(5px);
}
</style>
