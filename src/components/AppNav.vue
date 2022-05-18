<template>
  <nav>
        <ul>
            <li v-for="(link, index) in navLinks" :key="index">
                <a href="#">
                    <span>{{link}}</span>
                    <i class="fa-solid fa-chevron-down"></i>
                    <!-- prove -->
                    <div class="gray-border"></div>
                    <div class="orange-border"></div>
                </a>
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
        gap: 40px;
        list-style: none;
        li{
            a{
                text-decoration: none;
                color: $primary-text;
                text-transform: capitalize;
                font-weight: 500;
                font-size: $md-text;
                i{
                    font-size: $sm-text;
                    margin-left: 10px;
                    vertical-align: middle;
                }
                // prove
                height: 100%;
                background-color: transparent;
                display: inline-block;
                position: relative;
                overflow: hidden;
                padding: 3px 0;
                .gray-border, .orange-border{
                    height: 100%;
                    width: 100%;
                    position: absolute;
                    top: 0px;
                    transition: left 0.35s;
                    transition-timing-function: ease;
                }
                .gray-border{
                    border-bottom: 2px solid rgba($color: $gray-text, $alpha: 0);
                    left: 0;
                }
                .orange-border{
                    border-bottom: 2px solid $thunderbird;
                    left: 120%;
                }
                &:hover{
                    .gray-border{
                        left: -120%;
                    }
                    .orange-border{
                        left: 0;
                    }
                }
            }
        }
    }
}

</style>