<template>
    <section class="blog">

        <section-title :signature="'Articles and Tips'" :text="'Latest From The Blog'" />

        <blog-cards :myArray="appImgs.blog" />

        <div class="btn">
            <a href="#">
                <span>Get into details now?</span>
                <span class="icon">View all posts
                    <i class="fa-solid fa-arrow-right-long"></i>
                    <div class="gray-border"></div>
                    <div class="orange-border"></div>
                </span>
            </a>
        </div>

    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue'
import dati from '../immagini'
import BlogCards from './BlogCards.vue'

export default {
    components: {
        SectionTitle,
        BlogCards
    },
    name: 'SectionBlog',
    data(){return{
        appImgs: dati
    }}
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

    section{
        padding: $section-gap 0;
        background-color: $my-silver;
        .btn{
            text-align: center;
            a{
                @include transparent-btn;
                .gray-border, .orange-border{
                    height: 100%;
                    width: 100%;
                    position: absolute;
                    top: 0px;
                    transition: left 0.75s;
                    transition-timing-function: ease;
                }
                .gray-border{
                    border-bottom: 1px solid rgba($color: $gray-text, $alpha: 0.5);
                    left: 0;
                }
                .orange-border{
                    border-bottom: 1px solid $thunderbird;
                    left: 120%;
                }
            }
        }
        
    }

</style>