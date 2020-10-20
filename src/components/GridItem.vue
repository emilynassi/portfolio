<template>
  <div class="grid-container">
    <a
      v-for="project in projects"
      :key="project.id"
      :href="project.link"
      target="_blank"
      class="grid-item"
      :class="{ featured: project.featured }"
    >
      <template v-if="project.featured">
        <div class="title">
          <h3>{{ project.title }}</h3>
        </div>
        <div v-if="project.featured" class="description">
          <p>
            {{ project.description }}
          </p>
        </div>
        <div class="tech">
          <span v-for="tech in project.stack" :key="tech">{{ tech }}</span>
        </div>
      </template>
      <template v-else>
        <div>
          <h3>{{ project.title }}</h3>
          <div class="tech">
            <span v-for="tech in project.stack" :key="tech">{{ tech }}</span>
          </div>
        </div>
      </template>
    </a>
  </div>
</template>

<script>
import projects from '../assets/data/projects.json'

export default {
  name: 'GridItem',
  data() {
    return {
      projects: projects
    }
  }
}
</script>
