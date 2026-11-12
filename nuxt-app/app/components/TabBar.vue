<script setup>
// items: a list of { label, icon, to }. The tab bar shows one TabBarItem for each.
const props = defineProps({
  items: { type: Array, required: true }
})
</script>

<template>
  <nav aria-label="Hoofdmenu" class="flex rounded-card border border-line bg-surface px-2 py-3 shadow-sm">
    <TabBarItem
      v-for="item in props.items"
      :key="item.to"
      :label="item.label"
      :icon="item.icon"
      :to="item.to"
    />
  </nav>
</template>
