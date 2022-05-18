<template>
    <div class="footer-bottom">
        <div class="container">

            <div class="links">
                <ul class="general">
                    <li v-for="(item, index) in links" :key="index">
                        <!-- titolo -->
                        <div class="title" >
                            <span>{{item.title}}</span>
                            <span v-if="item.page" class="page">{{item.page}}</span>
                        </div>

                        <!-- links -->
                        <ul class="link" v-if="item.link">
                            <li v-for="(link, i) in item.link" :key="i">
                                {{link}}
                            </li>
                        </ul>
                        
                        <!-- immagini -->
                        <ul class="immagini" v-if="item.img">
                            <li v-for="(immagine, y) in item.img" :key="y">
                                <div class="img-box">
                                    <img :src="item.img[y]" :alt="'immagine instagram ' + y">
                                </div>
                            </li>
                        </ul>
                        
                        <!-- icone -->
                        <div class="icons" v-if="item.icons">
                            <i v-for="(icona, k) in item.icons" :key="k" class="fa-brands" :class="item.icons[k]"></i>
                        </div>
                        

                    </li>
                </ul>
            </div>

            <div class="copyright">
                <i class="fa-regular fa-copyright"></i>
                <span>2020 MaxCoach.  All Rights Reserved</span>
            </div>
        </div>
    </div>
</template>

<script>
import dati from '../immagini'

export default {
    name: 'FooterBottom',
    data(){
        return{
            links: dati.footer.links
        }
    }
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

.footer-bottom{
    padding: $section-gap 0;
    .container{
        @include container-lg;
        .links{
            ul.general{
                width: 100%;
                @include flex-row-between-start;
                gap: 50px;
                list-style: none;
                ul{
                    list-style: none;
                    li{
                        margin-top: 30px;
                    }
                }
                .title{
                    font-weight: 600;
                    text-transform: capitalize;
                    .page{
                        margin-left: 15px;
                        color: $thunderbird;
                        font-size: 0.8em;
                        text-transform: lowercase
                    }
                }
                ul.link{
                    @include flex-col-between-start;
                    font-size: $md-text;
                    font-weight: 500;
                    color: $boulder;
                }
                ul.immagini{
                    @include flex-row-end-center;
                    gap: 20px;
                    li{
                        .img-box{
                            height: 150px;
                            img{
                                height: 100%;
                                width: 100%;
                                object-fit: cover;
                                object-position: center;
                                transition: all 0.5s;
                                &:hover{
                                    filter: grayscale(100%);
                                }
                            }
                        }
                    }
                }
                div.icons{
                    margin-top: 50px;
                    @include flex-row-start-center;
                    gap: 15px;
                    i{
                        color: $gray-text;
                        font-size: $lg-text;
                    }
                }
            }
        }
        .copyright{
            text-align: center;
            margin-top: $section-gap;
            color: $gray-text;
        }
    }
}

</style>