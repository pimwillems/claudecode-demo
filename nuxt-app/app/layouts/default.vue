<script setup>
// The tabs of the app. Change this list to add, remove or rename a tab.
const tabs = [
  { label: 'Home', icon: 'mdi:home', to: '/' },
  { label: 'Kluis', icon: 'mdi:lock', to: '/kluis' },
  { label: 'Plannen', icon: 'mdi:file-document', to: '/plannen' },
  { label: 'Gedeeld', icon: 'mdi:swap-horizontal-bold', to: '/gedeeld' }
]
</script>

<template>
  <!-- Phone-sized column, centered on bigger screens -->
  <div class="mx-auto flex min-h-screen max-w-md flex-col px-5 pb-5 pt-6">
    <main class="flex-1">
      <slot />
    </main>
    <TabBar :items="tabs" class="mt-6" />
  </div>
</template>
