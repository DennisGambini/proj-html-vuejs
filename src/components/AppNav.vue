<template>
  <nav>
        <ul>
            <li v-for="(link, index) in navLinks" :key="index">
                <a href="#">{{link}}</a>
                <i class="fa-solid fa-chevron-down"></i>
            </li>
        </ul>
  </nav>
</template>

<script>
import dati from '../dati.json'

export default {
    name: 'AppNav',
    data(){return{
        navLinks: dati.navLinks
    }}
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

nav{
    ul{
        @include flex-row-between;
        gap: 20px;
        list-style: none;
        li{
            a{
                text-decoration: none;
                color: $primary-text;
                text-transform: capitalize;
            }
        }
    }
}

</style>