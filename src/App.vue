<script>
import Navbar from '../src/components/Navbar.vue'
import TheFooter from '../src/components/Footer.vue'
import Projects from '../src/components/Projects.vue'
import Technologies from '../src/components/Technologies.vue'
import About from '../src/components/About.vue'
import MainInfo from '../src/components/MainInfo.vue'

export default {
  components: { Navbar, Projects, Technologies, About, MainInfo, TheFooter },

  methods: {
    scrollToViewport(comp) {
      this.$refs[comp].scrollIntoView({ behavior: 'smooth' });
    }
  }
}
</script>

<template>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap')" rel="stylesheet">
  <div class="md:px-24 px-6 py-6">
    <Navbar @scrollToViewport="scrollToViewport" />
    <MainInfo />
    <div ref="projects">
      <Projects />
    </div>
    <div ref="technologies">
      <Technologies />
    </div>
    <div ref="aboutMe">
      <About />
    </div>
    <TheFooter />
  </div>
</template>

<style scoped></style>