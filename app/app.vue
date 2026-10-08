<template>
  <NuxtRouteAnnouncer />
  <PageRenderer :sections="page.sections" />
</template>

<script setup lang="ts">
import page from './data/home-page.json'
</script>
