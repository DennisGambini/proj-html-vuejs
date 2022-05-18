<template>
  <div id="app">

      <div class="maxi-container">
      <app-counterdown class="counter-clock"/>

        <app-header class="header"/>
        <app-jumbo/>

        <main>
          <first-section />
          <section-courses />
          <section-blog />
          <section-events />
        </main>
        
        <app-footer/>

      </div>
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
  },
  data(){
    return{

    }
  },
  mounted(){
    const header = document.querySelector('.header');
    const content = document.querySelector('.maxi-container');
    let limite = header.offsetTop;

    function myScroll(){
      if(window.scrollY > limite){
        header.classList.add('fixed')
        content.classList.add('padding')
      } else {
        header.classList.remove('fixed')
        content.classList.remove('padding')
      }
    }

    window.onscroll = function(){
      myScroll()
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/general.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  .maxi-container{
    position: relative;
  }
  .header{
    width: 100%;
  }
  .fixed{
    position: fixed;
    top: 0;
    width: 100%;
  }
  .padding{
    padding-top: 70px;
  }
  
}
</style>
