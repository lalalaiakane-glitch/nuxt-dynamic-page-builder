<script setup lang="ts">
defineProps<{
  title: string
  body: string
}>()
</script>

<template>
  <section class="rich-text">
    <h2>{{ title }}</h2>
    <p>{{ body }}</p>
  </section>
</template>

<style scoped>
.rich-text {
  padding: 32px 24px 80px;
  margin: 0 auto;
  max-width: 760px;
}

h2 {
  margin: 0;
  font-size: 28px;
}

p {
  margin: 12px 0 0;
  color: #4b4b45;
  font-size: 18px;
  line-height: 1.7;
}
</style>
