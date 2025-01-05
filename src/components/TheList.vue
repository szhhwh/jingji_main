<script setup lang="ts">
import ListItem from './ListItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import IconCommunity from './icons/IconCommunity.vue'
</script>

<template>
  <ListItem>
    <template #icon>
      <a href="https://book.jjnwxs.cn" target="_self"> <DocumentationIcon /></a>
    </template>
    <template #heading>
      <a href="https://book.jjnwxs.cn" target="_self" rel="noopener"
        >荆棘鸟文学社官方参考文档</a
      ></template
    >文学社规范文档和 Adobe Indesign 操作指南
  </ListItem>

  <ListItem>
    <template #icon>
      <a href="https://sp.jjnwxs.cn" target="_self"> <IconCommunity /></a>
    </template>
    <template #heading>
      <a href="https://sp.jjnwxs.cn" target="_self" rel="noopener"
        >荆棘鸟文学社高三特刊</a
      ></template
    >
    高三特刊各班级内容
  </ListItem>
</template>
