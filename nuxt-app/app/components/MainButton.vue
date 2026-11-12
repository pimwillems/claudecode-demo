<script setup>
// One big button for the main actions on a page.
// icon: name from https://icones.js.org (use the "mdi:" set)
const props = defineProps({
  label: { type: String, required: true },
  subtitle: { type: String, default: '' },
  icon: { type: String, required: true },
  to: { type: String, required: true }
})
</script>

<template>
  <NuxtLink
    :to="props.to"
    class="flex items-center gap-4 rounded-card border border-line bg-surface p-3 pr-5 shadow-sm hover:bg-white"
  >
    <span class="flex size-17 shrink-0 items-center justify-center rounded-tile bg-primary text-white">
      <Icon :name="props.icon" class="text-4xl" />
    </span>

    <span class="flex-1">
      <span class="block text-lg font-semibold text-ink">{{ props.label }}</span>
      <span v-if="props.subtitle" class="block text-base text-muted">{{ props.subtitle }}</span>
    </span>

    <Icon name="mdi:arrow-right" class="text-3xl text-primary" />
  </NuxtLink>
</template>
