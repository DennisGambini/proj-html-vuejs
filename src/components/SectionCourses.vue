<template>
    <section class="courses">
        <section-title :signature="'Artist coaching'" :text="'Latest Online Courses'" />
        <courses-cards :myArray="myArray.corsi"/>

        <a href="#">
          View all courses  
          <i class="fa-solid fa-arrow-right-long"></i>
        </a>

        <div class="scritta">courses</div>
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
            text-transform: uppercase;
            font-size: 100px;
            color: white;
            position: absolute;
            right: -10%;
            top: 50%;
            opacity: 0.3;
            z-index: -1;
            transform: translateY(-50%) rotate(90deg);
            text-shadow: 1px 1px  rgba($color: $matrix, $alpha: 0.15),
            1px -1px rgba($matrix, 0.15),
            -1px 1px rgba($matrix, 0.15),
            -1px -1px rgba($matrix, 0.15),
            2px 2px rgba($matrix, 0.15),
            2px -2px rgba($matrix, 0.15),
            -2px 2px rgba($matrix, 0.15),
            -2px -2px rgba($matrix, 0.15),
            3px 3px rgba($matrix, 0.15),
            3px -3px rgba($matrix, 0.15),
            -3px 3px rgba($matrix, 0.15),
            -3px -3px rgba($matrix, 0.15),
        }
}

</style>