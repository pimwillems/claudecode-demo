<script setup>
// The "Snel verder" shortcuts. Later this can come from an API.
const quickLinks = [
  { type: 'Actief plan', title: 'Sollicitatie software developer', to: '/plannen' },
  { type: 'Recent bewijs', title: 'HBO Diploma - ICT', to: '/kluis' },
  { type: 'Afgerond plan', title: 'Rijbewijs B', to: '/plannen' }
]
</script>

<template>
  <div>
    <AppHeader />

    <h1 class="mt-14 text-4xl font-semibold leading-tight text-ink">Goedemiddag, Ravi</h1>

    <div class="mt-16 flex flex-col gap-4">
      <MainButton label="Mijn kluis" subtitle="Al uw documenten op één plek." icon="mdi:lock-open" to="/kluis" />
      <MainButton label="Mijn plannen" subtitle="Werk aan uw volgende stap." icon="mdi:file-document" to="/plannen" />
    </div>

    <section class="mt-20 rounded-card border border-line bg-surface p-6">
      <h2 class="text-sm font-semibold uppercase tracking-wider text-muted">Snel verder</h2>
      <ul class="mt-4">
        <li v-for="link in quickLinks" :key="link.title" class="border-b border-line last:border-b-0">
          <NuxtLink :to="link.to" class="flex items-center justify-between py-3">
            <span>
              <span class="block text-sm text-muted">{{ link.type }}</span>
              <span class="block text-lg font-medium text-ink">{{ link.title }}</span>
            </span>
            <Icon name="mdi:arrow-right" class="text-3xl text-primary" />
          </NuxtLink>
        </li>
      </ul>
    </section>
  </div>
</template>
