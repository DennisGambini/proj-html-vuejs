<template>
  <div id="app">
    <app-counterdown/>
    <app-header/>
    <app-jumbo/>

    <main>
      <first-section />
      <section-courses />
    </main>
    
  </div>
</template>

<script>
import AppCounterdown from './components/AppCounterdown.vue'
import AppHeader from './components/AppHeader.vue'
import AppJumbo from './components/AppJumbo.vue'
import FirstSection from './components/FirstSection.vue'
import SectionCourses from './components/SectionCourses.vue'


export default {
  name: 'App',
  components: {
    AppHeader,
    AppCounterdown,
    AppJumbo,
    FirstSection,
    SectionCourses,
  }
}
</script>

<style lang="scss">
@import './assets/style/general.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  
}
</style>
