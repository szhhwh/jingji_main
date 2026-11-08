<script setup lang="ts">
import ListItem from './ListItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import IconCommunity from './icons/IconCommunity.vue'
</script>

<template>
  <nav class="nav-list" aria-label="站点导航">
    <ListItem href="https://book.jjnwxs.cn">
      <template #icon>
        <DocumentationIcon />
      </template>
      <template #heading>荆棘鸟文学社官方参考文档</template>
      文学社规范文档和 Adobe InDesign 操作指南
    </ListItem>

    <ListItem href="https://sp.jjnwxs.cn">
      <template #icon>
        <IconCommunity />
      </template>
      <template #heading>荆棘鸟文学社高三特刊</template>
      高三特刊各班级内容
    </ListItem>
  </nav>
</template>

<style scoped>
.nav-list {
  display: flex;
  flex-direction: column;
}
</style>
