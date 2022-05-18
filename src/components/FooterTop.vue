<template>
    <div class="footer-top">
        <div class="container">
            <div class="label">Newsletter to get in touch</div>
            <div class="form">
                <input type="email" name="email" id="email" placeholder="Your e-mail">
                <i class="fa-solid fa-arrow-right-long"></i>
            </div>

        </div>

        <img :src="imgsFooter.sfondoSx" alt="immagine di sfondo" class="sfondo-sx">
        <img :src="imgsFooter.sfondoDx" alt="immagine di sfondo" class="sfondo-dx">
    </div>
</template>

<script>
import dati from '../immagini'

export default {
    name: 'FooterTop',
    data(){
        return{
            imgsFooter: dati.footer.sfondi
        }
    }
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

.footer-top{
    height: 200px;
    background-color: $bay-of-many;
    position: relative;
    .container{
        height: 100%;
        @include container-md;
        @include flex-row-between-center;
        gap: 100px;
        color: $white;
        font-size: $xl-text;
        .label{
            width: 300px;
            text-align: end;
        }
        .form{
            flex-grow: 1;
            @include flex-row-start;
            z-index: 1;
            input{
                width: 100%;
                padding: 10px 0;
                background: none;
                border: none;
                border-bottom: 2px solid rgba($color: $white, $alpha: 0.5);
                color: $white;
                font-size: $lg-text;
                &:hover{
                    border-bottom: 2px solid rgba($color: $white, $alpha: 1);
                }
                &::placeholder{
                    color: $white;
                    font-size: $lg-text;
                    border: none;
                }
            }
            i{
                vertical-align: middle;
                position: relative;
                left: -30px;
            }
        }
    }
    .sfondo-dx, .sfondo-sx{
        position: absolute;
        top: 0;
        height: 100%;
    }
    .sfondo-sx{
        left: 0;
    }
    .sfondo-dx{
        right: 0;
    }
}

</style>