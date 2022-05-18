<template>
  <header>
        <div class="container">
            <!-- logo -->
            <div class="logo">
                <img :src="logo" alt="MaxCoach logo">
            </div>
            <!-- nav -->
            <app-nav/>
            <!-- icons -->
            <div class="icons">
                <i class="fa-brands fa-twitter"></i>
                <i class="fa-brands fa-facebook-f"></i>
                <i class="fa-brands fa-instagram"></i>
                <i class="fa-brands fa-linkedin"></i>
            </div>
        </div>
  </header>
</template>

<script>
import AppNav from './AppNav.vue'
export default {
    name: 'AppHeader',
    components: { 
        AppNav
    },
    data(){return{
        logo: require('../assets/images/dark-logo.png')
    }}

}
</script>


<style lang="scss" scoped>
@import '../assets/style/vars.scss';

header{
    height: 70px;
    z-index: 1000;
    background: $white;
    box-shadow: 0px 3px 10px rgba($color: #000000, $alpha: 0.2);
    .container{
        height: 100%;
        @include flex-row-between-center;
        @include container-lg;
        .logo{
            height: 20px;
            img{
                height: 100%;
            }
        }
        .icons{
            @include flex-row-between-center;
            gap: 20px;
            i{
                font-size: $lg-text;
                color: $gray-text;
                cursor: pointer;
                transition: 0.4s;
                &:hover{
                    color: $thunderbird;
                }
            }
        }
    }
}

</style>