<template>
  <header class="pt-24 md:pt-32 pb-16 md:pb-32">
    <h1
      class="name relative inline-block cursor-default text-[clamp(3rem,10vw,7rem)] font-bold tracking-tight leading-none mb-4"
      @mouseenter="startSparkles"
      @mouseleave="stopSparkles"
    >
      <span
        ref="sparkleContainer"
        class="absolute top-0 left-0 w-full h-full pointer-events-none overflow-visible"
      >
        <span class="sparkle"></span>
        <span class="sparkle"></span>
        <span class="sparkle"></span>
        <span class="sparkle"></span>
        <span class="sparkle"></span>
        <span class="sparkle"></span>
        <span class="sparkle"></span>
        <span class="sparkle"></span>
      </span>
      <span class="name-text relative inline-block transition-all duration-300"
        >Emily Rosenkranz</span
      >
    </h1>

    <p class="text-base md:text-lg leading-relaxed max-w-2xl mb-6 md:mb-8">
      Senior Software Developer at Teamworks, working on NIL and cap management tools. Builds hockey
      apps on the side because one sports job wasn't enough. Also runs and has strong opinions about
      music.
    </p>

    <div class="flex flex-wrap gap-2">
      <a
        v-for="link in links"
        :key="link.label"
        :href="link.href"
        :class="link.color"
        :target="link.target || '_self'"
        class="px-2.5 py-1 text-sm font-medium rounded text-black transition-colors"
        >{{ link.label }}</a
      >
    </div>
  </header>
</template>

<script setup lang="ts">
import { ref, useTemplateRef, onMounted } from 'vue';

/** Name Sparkle */
const sparkleContainer = useTemplateRef<HTMLElement>('sparkleContainer');
const sparkles = ref<HTMLElement[]>([]);
const sparkleInterval = ref<ReturnType<typeof setInterval> | null>(null);

onMounted(() => {
  if (sparkleContainer.value) {
    sparkles.value = Array.from(sparkleContainer.value.querySelectorAll('.sparkle'));
  }
});

function triggerRandomSparkle() {
  if (sparkles.value.length === 0) return;

  const sparkle = sparkles.value[Math.floor(Math.random() * sparkles.value.length)];
  if (!sparkle) return;

  const top = Math.random() * 100;
  const left = Math.random() * 100;

  sparkle.style.top = top + '%';
  sparkle.style.left = left + '%';

  sparkle.classList.remove('twinkle');
  void sparkle.offsetWidth;
  sparkle.classList.add('twinkle');
}

function startSparkles() {
  triggerRandomSparkle();
  setTimeout(triggerRandomSparkle, 100);
  setTimeout(triggerRandomSparkle, 200);
  sparkleInterval.value = setInterval(triggerRandomSparkle, 150);
}

function stopSparkles() {
  if (sparkleInterval.value) {
    clearInterval(sparkleInterval.value);
    sparkleInterval.value = null;
  }
}

interface Link {
  label: string;
  href: string;
  target?: '_blank' | '_self' | '_parent' | '_top';
  color?:
    | 'bg-tag-yellow'
    | 'bg-tag-pink'
    | 'bg-tag-green'
    | 'bg-tag-blue'
    | 'bg-tag-purple'
    | 'bg-tag-orange';
}

const links = ref<Link[]>([
  {
    label: 'GitHub',
    href: 'https://github.com/emilynassi',
    color: 'bg-tag-yellow',
    target: '_blank',
  },
  {
    label: 'LinkedIn',
    href: 'https://www.linkedin.com/in/emily-rosenkranz-aa6b4a20/',
    color: 'bg-tag-pink',
    target: '_blank',
  },
  {
    label: 'Email',
    href: 'mailto:emily.nassi1@gmail.com',
  },
  {
    label: 'Projects',
    href: '#projects',
  },
  {
    label: 'Posts',
    href: '#posts',
  },
]);
</script>
