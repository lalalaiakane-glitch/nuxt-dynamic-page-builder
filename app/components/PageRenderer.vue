<script setup lang="ts">
import HeroSection from './sections/HeroSection.vue'
import FeatureGridSection from './sections/FeatureGridSection.vue'
import RichTextSection from './sections/RichTextSection.vue'

type PageSection = {
  id: string
  type: string
  props: Record<string, unknown>
}

defineProps<{
  sections: PageSection[]
}>()

const sectionComponents = {
  hero: HeroSection,
  featureGrid: FeatureGridSection,
  richText: RichTextSection
} as const
</script>

<template>
  <main class="page">
    <template v-for="section in sections" :key="section.id">
      <component
        :is="sectionComponents[section.type as keyof typeof sectionComponents]"
        v-if="section.type in sectionComponents"
        v-bind="section.props"
      />
      <section v-else class="unknown-section">
        Unknown section type: {{ section.type }}
      </section>
    </template>
  </main>
</template>

<style scoped>
.page {
  min-height: 100vh;
  background: #f7f7f4;
  color: #161616;
}

.unknown-section {
  margin: 24px auto;
  max-width: 960px;
  border: 1px solid #c84d38;
  padding: 16px;
  color: #8f2f20;
}
</style>
