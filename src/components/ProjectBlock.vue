<template>
  <a
    :href="project.link"
    target="_blank"
    class="group flex flex-col gap-3"
  >
    <span class="text-[clamp(3rem,6vw,4.5rem)] font-bold tracking-tight leading-none">
      {{ project.year }}</span
    >
    <div class="flex flex-wrap gap-1.5">
      <span
        :class="['px-2.5 py-1 text-sm font-medium rounded text-black', getTagColor(tag)]"
        v-for="tag in project.tags"
        :key="tag"
        >{{ tag }}</span
      >
    </div>
    <h3 class="text-base font-semibold mt-1">{{ project.title }}</h3>
    <span
      class="text-sm text-text-muted group-hover:text-text-primary transition-colors break-all"
      >{{ project.link }}</span
    >
    <p class="text-[0.9375rem] leading-normal max-w-xs">
      {{ project.description }}
    </p>
  </a>
</template>

<script setup lang="ts">
export interface Project {
  year: number;
  tags: string[];
  title: string;
  link: string;
  description: string;
}

interface TagMap {
  [key: string]: string;
}

const tagMap: TagMap = {
  Vue: 'bg-tag-green',
  TypeScript: 'bg-tag-blue',
  JavaScript: 'bg-tag-yellow',
  'Node.js': 'bg-tag-green',
  React: 'bg-tag-blue',
  'Next.js': 'bg-tag-yellow',
};

const props = defineProps<{
  project: Project;
}>();

const getTagColor = (tag: string): string => {
  return tagMap[tag] || 'bg-gray-500'; // Default fallback color
};
</script>
