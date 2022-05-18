<template>
  <div id="app">
    <app-counterdown/>
    <app-header/>
    <app-jumbo/>

    <main>
      <first-section />
      <section-courses />
      <section-blog />
      <section-events />
    </main>
    
    <app-footer/>
  </div>
</template>

<script>
import AppCounterdown from './components/AppCounterdown.vue'
import AppHeader from './components/AppHeader.vue'
import AppJumbo from './components/AppJumbo.vue'
import FirstSection from './components/FirstSection.vue'
import SectionBlog from './components/SectionBlog.vue'
import SectionCourses from './components/SectionCourses.vue'
import SectionEvents from './components/SectionEvents.vue'
import AppFooter from './components/AppFooter.vue'


export default {
  name: 'App',
  components: {
    AppHeader,
    AppCounterdown,
    AppJumbo,
    FirstSection,
    SectionCourses,
    SectionBlog,
    SectionEvents,
    AppFooter
  }
}
</script>

<style lang="scss">
@import './assets/style/general.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  
}
</style>
