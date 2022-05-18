<template>
    <section class="courses">
        <section-title :signature="'Artist coaching'" :text="'Latest Online Courses'" />
        <courses-cards :myArray="myArray.corsi"/>

        <a href="#">
          View all courses  
          <i class="fa-solid fa-arrow-right-long"></i>
        </a>

        <scritta-sfondo :scritta="'courses'" class="scritta"/>

        <img :src="myArray.sfondi.fagiolo" alt="sfondo artista" class="fagiolo">
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue'
import dati from '../immagini'
import CoursesCards from './CoursesCards.vue'
import ScrittaSfondo from './ScrittaSfondo.vue'

export default {
    components: { 
        SectionTitle,
        CoursesCards,
        ScrittaSfondo,
    },
    name: 'SectionCourses',
    data(){return{
        myArray: dati
    }}
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

section{
    padding: $section-gap 0;
    text-align: center;
    position: relative;
    a{
        @include light-btn;
        i{
            vertical-align: middle;
        }
    }
    .scritta{
        position: absolute;
        right: -15%;
        top: 50%;
    }
    .fagiolo{
        z-index: -1;
        position: absolute;
        left: -10%;
        top: 50%;
        transform: translateY(-50%);
        opacity: 1;
        filter: opacity(0.7) drop-shadow(0 0 0 blue);
    }
}

</style>