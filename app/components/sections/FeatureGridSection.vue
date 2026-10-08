<script setup lang="ts">
defineProps<{
  title: string
  items: Array<{
    title: string
    description: string
  }>
}>()
</script>

<template>
  <section class="feature-grid">
    <h2>{{ title }}</h2>
    <div class="items">
      <article v-for="item in items" :key="item.title">
        <h3>{{ item.title }}</h3>
        <p>{{ item.description }}</p>
      </article>
    </div>
  </section>
</template>

<style scoped>
.feature-grid {
  padding: 32px 24px;
  margin: 0 auto;
  max-width: 960px;
}

h2 {
  margin: 0 0 18px;
  font-size: 28px;
}

.items {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
  gap: 14px;
}

article {
  border: 1px solid #deded6;
  border-radius: 8px;
  background: white;
  padding: 18px;
}

h3,
p {
  margin: 0;
}

p {
  margin-top: 8px;
  color: #565650;
  line-height: 1.5;
}
</style>
