<template>
  <section class="first-section">
      <div class="cards">
          <div class="container">
                <div class="text">
                    <div class="signature">Artist coaching</div>
                    <h2>I understand what it taked to create. <br>
                    I can help you with
                    </h2>
                </div>

                <div class="row">
                    <div class="card" v-for="(card, index) in cards" :key="index">
                        <img :src="imgs[index].img" :alt="card.title + ' img'">
                        <h4>{{card.title}}</h4>
                        <p>{{card.description}}</p>
                    </div>
                </div>
          </div>
          
      </div>
      <div class="quote">
          <div class="container">
              <div class="sx">
                  <img :src="quoteImg" alt="quote">
                  <h2>I coach and mentor visual artists, like you, to Create Like You Mean It</h2>
                  <div class="sign">Martin Garrix</div>
              </div>
              <div class="dx">
                  <p>As a coach and mentor, my ultimate goal is to motivate visual artists toward inspired action. I help you get you back on track to being the productive, creative, meaningful and authentic artist you truly want to be. I support artists in crafting and living a creative life as well as feeling good about themselves and their art.</p>
                  <p>As an artist and an educator for nearly 30 years, I understand what it takes to create.</p>
                  <a role="button" href="#">Get started today</a>
              </div>
          </div>
      </div>
      <div class="embed">

      </div>
      <div class="carousel">

      </div>
  </section>
</template>

<script>
import dati from '@/dati.json';

export default {
    name: 'FirstSection',
    data(){return{
        cards: dati.cards,
        imgs:[
            {
                img: require('@/assets/images/artist-box-image-01.png')
            },
            {
                img: require('@/assets/images/artist-box-image-02.png')
            },
            {
                img: require('@/assets/images/artist-box-image-03.png')
            },
            {
                img: require('@/assets/images/artist-box-image-04.png')
            },
        ],
        quoteImg: require('@/assets/images/artist-quote-icon.png')
    }},
    methods:{

    }
    
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
        .text{
            @include flex-col-between-center;
            text-align: center;
            .signature{
                @include signature-text;
            }
        }
        .row{
            @include flex-row-between;
            margin-top: $section-gap;
            gap: 40px;
            .card{
                width: calc(100% / 4);
                &:nth-of-type(2), &:nth-of-type(4){
                    position: relative;
                    top: 60px;
                }
                p{
                    color: $gray-text;
                }
            }
        }
    }
    .quote{
        .sx{
            @include flex-col-between-center;
            width: 50%;
            float: left;
            text-align: center;
            img{
                height: 25px;
            }
            .sign{
                @include signature-text;
            }
        }
        .dx{
            padding-top: 25px;
            width: 50%;
            float: left;
            a{
                @include orange-sm-btn;
            }
            p{
                color: $gray-text;
            }
        }
    }
}
</style>