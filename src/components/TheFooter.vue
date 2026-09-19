<script setup lang="ts">
import { ref } from 'vue'

const year = ref(new Date().getFullYear())
</script>

<template>
  <div class="footer-wrapper">
    <div class="footer">版权所有 &copy; 2023-{{ year }} 荆棘鸟文学社</div>
  </div>
</template>

<style scoped>
.footer-wrapper {
  position: absolute;
  bottom: 0;
  width: 100%;
  text-align: center;
  display: flex;
  justify-items: center;
  justify-content: space-evenly;
  align-items: center;
  .footer {
    font-size: 14px;
    margin-top: 8px;
    margin-left: 16px;
    margin-right: 16px;
    margin-bottom: 8px;
    display: block;
  }
}
</style>
