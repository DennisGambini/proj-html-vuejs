<template>
    <div class="jumbo">
        <div class="sx">
            <forma-strana class="mia-forma" />
            <img :src="sfondoSx" alt="immagine" class="sfondo-sx">
            <img :src="testa" alt="testa image" class="testa">
            <img :src="nebbia" alt="nebbia image" class="nebbia">
            <img :src="scarabocchio" alt="scarabocchio image" class="scarab">
            <img :src="scimmia" alt="scimmia image" class="scimmia">
        </div>

        <div class="text">
            <div class="signature">Hello, Im Matin</div>
            <h2>Artist Coaching And Mentoring Might Be for You</h2>
            <a href="#">Get started today</a>
        </div>

        <div class="dx">
            <img :src="sfondoDx" alt="immagine" class="sfondo-dx">
            <forma-strana class="mia-forma"/>
            <img :src="foglia" alt="foglia immagine" class="foglia">
            <img :src="paint" alt="paint image" class="paint">
            <img :src="rombo" alt="rombo image" class="rombo">
            <img :src="faccia" alt="faccia image" class="faccia">
        </div>
    </div>
</template>

<script>
import FormaStrana from './FormaStrana.vue'
export default {
  components: { FormaStrana },
    name: 'AppJumbo',
    data(){return{
        sfondoSx: require('../assets/images/artist-shape-02.png'),
        sfondoDx: require('../assets/images/artist-shape-01.png'),
        testa: require('../assets/images/artist-hero-image-03.png'),
        scimmia: require('../assets/images/artist-hero-image-01.jpg'),
        scarabocchio: require('../assets/images/artist-hero-image-02.jpg'),
        foglia: require('../assets/images/artist-shape-04.png'),
        nebbia: require('../assets/images/artist-shape-03.png'),
        rombo: require('../assets/images/maxcoach-shape-12.png'),
        paint: require('../assets/images/artist-shape-05.png'),
        faccia: require('../assets/images/artist-hero-image-04.jpg')
    }}
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
            @include centered;
            width: 30%;
            .signature{
                @include signature-text;
            }
            a{
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