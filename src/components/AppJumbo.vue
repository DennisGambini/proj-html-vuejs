<template>
    <div class="jumbo">
        <div class="sx">
            <forma-strana class="mia-forma" />
            <img :src="img.sfondi.semicerchio" alt="immagine" class="sfondo-sx">
            <img :src="img.sfondi.testa" alt="testa image" class="testa">
            <img :src="img.sfondi.nebbia" alt="nebbia image" class="nebbia">
            <img :src="img.sfondi.schizzo" alt="scarabocchio image" class="scarab">
            <img :src="img.sfondi.scimmia" alt="scimmia image" class="scimmia">
        </div>

        <div class="text">
            <div class="signature">Hello, Im Matin</div>
            <h2>Artist Coaching And Mentoring Might Be for You</h2>
            <a href="#">Get started today</a>
        </div>

        <div class="dx">
            <img :src="img.sfondi.fagiolo" alt="immagine" class="sfondo-dx">
            <forma-strana class="mia-forma"/>
            <img :src="img.sfondi.foglia" alt="foglia immagine" class="foglia">
            <img :src="img.sfondi.paint" alt="paint image" class="paint">
            <img :src="img.sfondi.pallaScura" alt="rombo image" class="rombo">
            <img :src="img.sfondi.faccia" alt="faccia image" class="faccia">
        </div>
    </div>
</template>

<script>
import FormaStrana from './FormaStrana.vue'
import immagini from '../immagini.js'

export default {
  components: { FormaStrana },
    name: 'AppJumbo',
    data(){return{
        img: immagini
    }},
    mounted(){
        const faccia = document.querySelector('.faccia');
        const scimmia = document.querySelector('.scimmia');
        const schizzo = document.querySelector('.scarab');

        const faceMove = (e) => {
            faccia.style.right = (e.pageX / 8) + 'px';
            faccia.style.bottom = (e.pageY / 8) + 'px';
        }
        const scimmiaMove = (e) => {
            scimmia.style.left = -(e.pageX / 20) +150 + 'px';
            scimmia.style.bottom = (e.pageY / 8) + 'px';
        }
        const schizzoMove = (e) => {
            schizzo.style.left = (e.pageX / 8) + 'px';
            schizzo.style.top = (e.pageY / 8) +100 + 'px';
        }

        document.addEventListener('mousemove', faceMove);
        document.addEventListener('mousemove', scimmiaMove)
        document.addEventListener('mousemove', schizzoMove)

    }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';
    
    .jumbo{
        height: 85vh;
        background-color: $hint-of-red;
        position: relative;
        img{
            position: absolute;
        }

        .sx{
            .sfondo-sx{
                top: 0;
                left: 0;
                width: 45%;
            }
            .testa{
                bottom: 50px;
                left: 25%;
                height: 260px;
            }
            .scarab{
                width: 200px;
                top: 100px;
                left: 15%;
                @include ombra-light;
            }
            .nebbia{
                height: 60%;
                top: 60%;
                transform: translateY(-50%);
                left: 50px;
            }
            .mia-forma{
                position: absolute;
                bottom: -100px;
                left: 200px;
                height: 600px;
                transform: rotate(40deg);
            }
            .scimmia{
                bottom: 70px;
                left: 140px;
                height: 200px;
                @include ombra-light;
            }
        }
        .text{
            @include flex-col-between-center;
            // gap: 20px;
            @include centered;
            width: 30%;
            .signature{
                @include signature-text;
                font-weight: 900;
                font-size: $huge-text;
            }
            h2{
                font-size: $xl-text;
            }
            a{
                margin-top: 40px;
                display: block;
                @include orange-md-btn;
            }
        }
        .dx{
            .sfondo-dx{
                top: 0;
                right: 150px;
                height: 90%;
            }
            .mia-forma{
                position: absolute;
                bottom: 10px;
                right: 450px;
                height: 300px;
                transform: rotate(40deg);
                @include yellow-filter;
            } 
            .foglia{
                top: 50px;
                right: 150px;
                height: 200px;
            }
            .rombo{
                bottom: 50px;
                right: 350px;
                height: 150px;
            }
            .paint{
                bottom: 10px;
                right: 170px;
                height: 180px;
            }
            .faccia{
                height: 300px;
                right: 270px;
                bottom: 70px;
            }
            
        }
    }
    
</style>