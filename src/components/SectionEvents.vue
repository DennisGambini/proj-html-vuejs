<template>
  <section class="events">
      <div class="container">
        <section-title :signature="'Upcoming Events'" :text="'Let\'s Work Together'" />

        <event-cards :myArray="appImgs.events" />

        <scritta-sfondo :scritta="'events'" />
        
      </div>
  </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue'
import dati from '../immagini'
import EventCards from './EventCards.vue'
import ScrittaSfondo from './ScrittaSfondo.vue'

export default {
    components: { 
        SectionTitle,
        EventCards,
        ScrittaSfondo 
    },
    name: 'SectionEvents',
    data(){return{
        appImgs: dati
    }}
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

section.events{ 
    padding: $section-gap 0;
    position: relative;
    .container{
        @include container-md;
    }
    .scritta{
        position: absolute;
        left: -10%;
        bottom: 20%;
    }
}

</style>