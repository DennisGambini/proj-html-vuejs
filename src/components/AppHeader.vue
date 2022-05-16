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
    .container{
        @include flex-row-between-center;
        @include container-md;
        .logo{
            height: 20px;
            img{
                height: 100%;
            }
        }
    }
}

</style>