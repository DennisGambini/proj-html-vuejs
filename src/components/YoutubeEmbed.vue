<template>
    <div class="box">
        <img :src="imgs.youtube.jumbo" alt="youtube video" class="jumbo">
        <forma-strana class="mia-forma sfondo" />
        <img :src="imgs.sfondi.pallaBlu" alt="sfondo" class="sfondo palla-blu">
        <img :src="imgs.sfondi.pallaScura" alt="sfondo" class="sfondo palla-scura">
        <div class="sfondo cerchio"></div>
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
        .jumbo{
            width: 100%;
        }

        .sfondo{
            position: absolute;
        }
        .mia-forma{
            z-index: -2;
            top: -50px;
            left: 50px;
            height: 350px;
            transform: rotate(140deg);
        }
        .palla-blu{
            left: 0;
            top: 30px;
        }
        .palla-scura{
            bottom: 50px;
            right: -50px;
        }
        .cerchio{
            height: 70px;
            width: 70px;
            border: 10px solid $tussock-vibrant;
            border-radius: 50%;
            top: 170px;
            right: 20px;
        }
        
    }

</style>