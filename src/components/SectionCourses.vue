<template>
    <section class="courses">
        <section-title :signature="'Artist coaching'" :text="'Latest Online Courses'" />
        <courses-cards :myArray="myArray.corsi"/>

        <a href="#">
          View all courses  
          <i class="fa-solid fa-arrow-right-long"></i>
        </a>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue'
import dati from '../immagini'
import CoursesCards from './CoursesCards.vue'

export default {
    components: { 
        SectionTitle,
        CoursesCards,
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
    padding-top: $section-gap;
    text-align: center;
    a{
        @include orange-md-btn;
        i{
            vertical-align: middle;
        }
    }
}

</style>