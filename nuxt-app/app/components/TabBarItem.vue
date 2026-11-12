<script setup>
// One tab: an icon, a label and a link.
const props = defineProps({
  label: { type: String, required: true },
  icon: { type: String, required: true },
  to: { type: String, required: true }
})
</script>

<template>
  <!-- NuxtLink adds the class "router-link-exact-active" when this is the current page.
       Tailwind's "aria-[current=page]:" variant styles that state. -->
  <NuxtLink
    :to="props.to"
    class="flex flex-1 flex-col items-center gap-1 py-1 text-sm font-medium text-muted aria-[current=page]:text-primary"
  >
    <Icon :name="props.icon" class="text-3xl" />
    <span>{{ props.label }}</span>
  </NuxtLink>
</template>
