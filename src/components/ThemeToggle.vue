<template>
  <!-- THEME TOGGLE -->
  <button
    id="themeToggle"
    @click="toggleTheme"
    aria-label="Toggle theme"
    class="fixed top-6 right-6 w-11 h-11 rounded-full bg-bg-secondary text-text-primary flex items-center justify-center cursor-pointer z-50 transition-transform duration-200 hover:scale-110"
  >
    <svg
      :class="['w-5 h-5 sun-icon', { hidden: theme !== 'dark' }]"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
    >
      <circle
        cx="12"
        cy="12"
        r="5"
      ></circle>
      <line
        x1="12"
        y1="1"
        x2="12"
        y2="3"
      ></line>
      <line
        x1="12"
        y1="21"
        x2="12"
        y2="23"
      ></line>
      <line
        x1="4.22"
        y1="4.22"
        x2="5.64"
        y2="5.64"
      ></line>
      <line
        x1="18.36"
        y1="18.36"
        x2="19.78"
        y2="19.78"
      ></line>
      <line
        x1="1"
        y1="12"
        x2="3"
        y2="12"
      ></line>
      <line
        x1="21"
        y1="12"
        x2="23"
        y2="12"
      ></line>
      <line
        x1="4.22"
        y1="19.78"
        x2="5.64"
        y2="18.36"
      ></line>
      <line
        x1="18.36"
        y1="5.64"
        x2="19.78"
        y2="4.22"
      ></line>
    </svg>
    <svg
      :class="['w-5 h-5 moon-icon', { hidden: theme === 'dark' }]"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      stroke-width="2"
      stroke-linecap="round"
      stroke-linejoin="round"
    >
      <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path>
    </svg>
  </button>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

const theme = ref<'light' | 'dark'>('light');

const toggleTheme = () => {
  theme.value = theme.value === 'light' ? 'dark' : 'light';
  document.documentElement.classList.toggle('dark', theme.value === 'dark');
  localStorage.setItem('theme', theme.value);
};

onMounted(() => {
  const savedTheme = localStorage.getItem('theme') as 'light' | 'dark' | null;

  if (savedTheme) {
    // User has manually set a preference
    theme.value = savedTheme;
  } else {
    // Check system preference
    const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
    theme.value = prefersDark ? 'dark' : 'light';
  }

  if (theme.value === 'dark') {
    document.documentElement.classList.add('dark');
  }
});
</script>
