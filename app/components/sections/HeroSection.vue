<script setup lang="ts">
defineProps<{
  eyebrow: string
  title: string
  description: string
  primaryAction: string
}>()
</script>

<template>
  <section class="hero">
    <p class="eyebrow">{{ eyebrow }}</p>
    <h1>{{ title }}</h1>
    <p class="description">{{ description }}</p>
    <button type="button">{{ primaryAction }}</button>
  </section>
</template>

<style scoped>
.hero {
  display: grid;
  gap: 18px;
  padding: 80px 24px 56px;
  margin: 0 auto;
  max-width: 960px;
}

.eyebrow {
  margin: 0;
  color: #3d6f5f;
  font-weight: 700;
  text-transform: uppercase;
}

h1 {
  margin: 0;
  max-width: 760px;
  font-size: clamp(40px, 8vw, 76px);
  line-height: 1;
}

.description {
  margin: 0;
  max-width: 620px;
  color: #4b4b45;
  font-size: 20px;
  line-height: 1.6;
}

button {
  width: fit-content;
  border: 0;
  border-radius: 6px;
  background: #161616;
  color: white;
  padding: 12px 18px;
  font-weight: 700;
}
</style>
