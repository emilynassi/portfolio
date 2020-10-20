<template>
  <main class="page-wrapper">
    <section id="about" class="page-section">
      <h2>About</h2>
      <div>
        <p>
          I am a front-end developer designing applications from the ground up.
          I help clients and companies recognize their visions through a
          combination of lo-fi mockups and hi-def wireframes, along with UX
          research, and make them come to life with Javascript, HTML, and CSS.
        </p>
        <p>
          My specialties include Vue, Node, SCSS, Bootstrap, and even Backbone.
          I create my wireframes with Adobe XD. I recently have worked in the
          e-commerce space for a variety of industries. I live in New Jersey and
          spend time cooking, running, and engaging in various house projects.
        </p>
      </div>
    </section>
    <section id="work" class="page-section">
      <h2>Work</h2>
      <GridItem />
    </section>
  </main>
</template>

<script lang="js">
import GridItem from '../components/GridItem.vue'
// import projects from '../assets/data/projects.json'

export default {
  name: 'Main',
  components : {
    GridItem
  }
}
</script>
