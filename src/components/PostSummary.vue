<template>
  <a
    href="#"
    class="group flex flex-col gap-2"
  >
    <span class="text-[clamp(2.5rem,5vw,3.5rem)] font-bold tracking-tight leading-none">
      {{ post.date }}</span
    >
    <span
      class="px-2.5 py-1 text-[0.8125rem] font-medium rounded bg-bg-secondary w-fit"
      v-for="tag in post.tags"
      :key="tag"
    >
      {{ tag }}
    </span>
    <h3 class="text-base font-semibold mt-1 max-w-xs group-hover:underline">
      {{ post.title }}
    </h3>
    <p class="text-[0.9375rem] leading-normal text-text-muted max-w-xs">
      {{ post.description }}
    </p>
  </a>
</template>

<script setup lang="ts">
export interface Post {
  date: string;
  tags: string[];
  title: string;
  description: string;
}

defineProps<{
  post: Post;
}>();
</script>
