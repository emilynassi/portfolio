<template>
   <header>
    <h1>Emily Rosenkranz</h1>
    <nav>
      <a href="#about">About Me</a>
      <a href="#work">Work</a>
      <a href="#contact">Contact Me</a>
      <a
        href="https://docs.google.com/document/d/16-55lyIlM9nRUx1U9H9ajUxr4-ykV1B4FzWz6YvrwLc/edit?usp=sharing"
        >Resume</a
      >
    </nav>
  </header>
</template>

<script>
export default {
  name: "NavBar",
  props: {
    headline: String
  }
};
</script>
