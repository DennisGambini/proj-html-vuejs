<template>
    <div class="box">
        <div class="jumbo-box">
            <img :src="imgs.youtube.jumbo" alt="youtube video" class="jumbo">
        </div>
        <forma-strana class="mia-forma sfondo" />
        <img :src="imgs.sfondi.pallaBlu" alt="sfondo" class="sfondo palla-blu">
        <img :src="imgs.sfondi.pallaScura" alt="sfondo" class="sfondo palla-scura">
        <div class="sfondo cerchio"></div>
        <img :src="imgs.youtube.logo" alt="youtube logo" class="sfondo logo">
    </div>
</template>

<script>
import immagini from '../immagini.js'
import FormaStrana from './FormaStrana.vue'

export default {
    name: 'YoutubeEmbed',
    components:{ FormaStrana },
    data(){return{
        imgs: immagini
    }}
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

    .box{
        margin-top: 230px;
        padding: 10vh 10vh;
        position: relative;
        
        .jumbo-box{
            margin: 0 auto;
            overflow: hidden;
            height: 400px;
            width: 100%;
            position: relative;
            .jumbo{
                @include centered;
                object-fit: cover;
                object-position: center;
                height: 100%;
                width: 100%;
                transition: all 1.5s ease-out;
            }
        }
        &:hover{
            .jumbo{
                height: 120%;
                width: 120%;
            }
        }

        .sfondo{
            position: absolute;
        }
        .mia-forma{
            z-index: -2;
            top: -40px;
            left: 50px;
            height: 350px;
            transform: rotate(140deg);
        }
        .palla-blu{
            left: 50px;
            top: 50px;
            z-index: -1;
            height: 150px;
        }
        .palla-scura{
            bottom: 50px;
            right: -40px;
            z-index: -1;
            height: 150px;
        }
        .cerchio{
            z-index: 10;
            height: 70px;
            width: 70px;
            border: 10px solid $tussock-vibrant;
            border-radius: 50%;
            top: 170px;
            right: 20px;
        }
        .logo{
            @include centered;
            height: 60px;
            transition: all 0.25s;
            cursor: pointer;
            &:hover{
                height: 65px;
            }
        }
        
    }

</style>