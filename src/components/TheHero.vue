<script setup lang="ts">
defineProps<{
  msg: string
}>()
</script>

<template>
  <div class="greetings">
    <h1 class="blue">{{ msg }}</h1>
    <h3>欢迎来到荆棘鸟文学社官网</h3>
  </div>
</template>

<style scoped>
.blue {
  text-decoration: none;
  background: linear-gradient(90deg, #00c6ff, #932be4);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
