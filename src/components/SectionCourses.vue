<template>
    <section class="courses">
        <section-title :signature="'Artist coaching'" :text="'Latest Online Courses'" />
        <courses-cards :myArray="myArray.corsi"/>

        <a href="#">
          View all courses  
          <i class="fa-solid fa-arrow-right-long"></i>
        </a>

        <!-- <div class="scritta">courses</div> -->
        <scritta-sfondo :scritta="'courses'" class="scritta"/>
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
        @include orange-md-btn;
        i{
            vertical-align: middle;
        }
    }
    .scritta{
        position: absolute;
        right: -15%;
        top: 50%;
    }
}

</style>