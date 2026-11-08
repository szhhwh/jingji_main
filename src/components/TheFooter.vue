<script setup lang="ts">
import { ref } from 'vue'

const year = ref(new Date().getFullYear())
</script>

<template>
  <footer class="footer-wrapper">
    <p class="footer">版权所有 &copy; 2023-{{ year }} 荆棘鸟文学社</p>
  </footer>
</template>

<style scoped>
.footer-wrapper {
  width: 100%;
  padding: 1.5rem 0 2rem;
  text-align: center;
}

.footer {
  font-size: 0.85rem;
  color: var(--text-muted);
  letter-spacing: 0.03em;
}
</style>
