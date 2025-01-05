<script setup lang="ts">
import ListItem from './ListItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
</script>

<template>
  <ListItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>荆棘鸟文学社参考文档</template>
    <a href="https://book.jjnwxs.cn" target="_blank" rel="noopener">荆棘鸟文学社官方参考文档</a>
    <br />包含 Adobe Indesign 操作指南和文学社规范文档。
  </ListItem>

  <ListItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>荆棘鸟文学社高三特刊</template>
    <a href="https://sp.jjnwxs.cn" target="_blank" rel="noopener">高三特刊</a>
  </ListItem>
</template>
