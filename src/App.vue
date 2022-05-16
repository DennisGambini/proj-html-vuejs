<template>
  <div id="app">
    <app-counterdown/>
    <app-header/>

    <main>
      <app-jumbo/>
    </main>
  </div>
</template>

<script>
import AppCounterdown from './components/AppCounterdown.vue'
import AppHeader from './components/AppHeader.vue'
import AppJumbo from './components/AppJumbo.vue'


export default {
  name: 'App',
  components: {
    AppHeader,
    AppCounterdown,
    AppJumbo

  }
}
</script>

<style lang="scss">
@import './assets/style/general.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  
}
</style>
