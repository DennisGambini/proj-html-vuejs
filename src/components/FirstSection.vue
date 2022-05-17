<template>
    <section class="first-section">

        <div class="cards">
            <!-- sfondi -->
            <img :src="appImgs.sfondi.fagiolo" alt="sfondo image" class="sfondo sfondo-dx">
            <img :src="appImgs.sfondi.linea" alt="sfondo linea" class="sfondo linea">
            <forma-strana class="sfondo forma-strana"/>
            <img :src="appImgs.sfondi.pallaOnde" alt="sfondo palla" class="sfondo palla">


            <div class="container">
                <first-cards :appImgs="appImgs"/>
            </div>
          
        </div>

        <!-- quote -->
        <div class="quote">
            <div class="container">
                <first-section-quote :mySource="appImgs.sfondi.quote"/>
            </div>
        </div>

        <!-- youtube -->
        <div class="embed">
            <div class="container">
                <youtube-embed/>
            </div>
        </div>

        <!-- carosello -->
        <div class="carousel">
            <section-title 
            :signature="'Testimonials'" :text="'Why do people love me?'"/>

            <app-carousel :myArray="appImgs.avatar"/>
        </div>

    </section>
</template>

<script>
import dati from '@/dati.json';
import immagini from '@/immagini.js'
import FormaStrana from './FormaStrana.vue';
import FirstCards from './FirstCards.vue';
import FirstSectionQuote from './FirstSectionQuote.vue';
import YoutubeEmbed from './YoutubeEmbed.vue';
import SectionTitle from './SectionTitle.vue';
import AppCarousel from './AppCarousel.vue';

export default {
  components: { FormaStrana, FirstCards, FirstSectionQuote, YoutubeEmbed, SectionTitle, AppCarousel },
    name: 'FirstSection',
    data(){return{
        cards: dati.cards,
        appImgs: immagini
    }}
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

.container{
    @include container-sm;
}
section{
    padding-top: $section-gap;
    .cards{
        padding-bottom: calc($section-gap * 2);
        position: relative;
        // sfondi
        >img, >.forma-strana{
            position: absolute;
            z-index: -1;
            top: 1000px;
        }
        .sfondo-dx{
            height: 500px;
            left: -50px;
            top: 0;
            transform: rotate(240deg);
            z-index: -2;
        } 
        .linea{
            top: 0;
            width: 100%;
        } 
        .forma-strana{
            top: 50px;
            right: 350px;
            height: 500px;
            @include rose-filter;
            z-index: -2;
        } 
        .palla{
            top: 50px;
            right: -50px;
            height: 150px;
        }
    }
}
</style>