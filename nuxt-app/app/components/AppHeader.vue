<script setup>
// backTo: the page the back button goes to. Leave it empty for no back button.
// initials: the letters shown in the profile circle.
const props = defineProps({
  backTo: { type: String, default: '' },
  initials: { type: String, default: 'RS' }
})
</script>

<template>
  <header class="flex items-center justify-between">
    <!-- Left: back button (or an empty block so the logo stays centered) -->
    <NuxtLink
      v-if="props.backTo"
      :to="props.backTo"
      aria-label="Terug"
      class="flex size-11 items-center justify-center rounded-full border border-line bg-surface text-primary"
    >
      <Icon name="mdi:arrow-left" class="text-2xl" />
    </NuxtLink>
    <div v-else class="size-11" />

    <!-- Middle: logo, links to home -->
    <NuxtLink to="/" aria-label="Naar home">
      <AppLogo />
    </NuxtLink>

    <!-- Right: profile circle -->
    <NuxtLink
      to="/profiel"
      aria-label="Mijn profiel"
      class="flex size-11 items-center justify-center rounded-full bg-primary text-base font-bold text-white"
    >
      {{ props.initials }}
    </NuxtLink>
  </header>
</template>
