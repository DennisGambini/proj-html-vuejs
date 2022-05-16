<template>
  <div>
      <!--?xml version="1.0" standalone="no"?-->              <svg id="sw-js-blob-svg" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">                    <defs>                         <linearGradient id="sw-gradient" x1="0" x2="1" y1="1" y2="0">                            <stop id="stop1" stop-color="rgba(248, 117, 55, 1)" offset="0%"></stop>                            <stop id="stop2" stop-color="rgba(251, 168, 31, 1)" offset="100%"></stop>                        </linearGradient>                    </defs>                <path fill="url(#sw-gradient)" d="M17.5,-35.4C19.5,-29.1,15.8,-18.1,16.9,-11.4C17.9,-4.7,23.6,-2.3,26.7,1.8C29.8,5.9,30.2,11.8,27.2,15.1C24.3,18.4,17.8,19.1,12.7,23.3C7.6,27.6,3.8,35.3,-0.3,35.9C-4.5,36.5,-9,30,-11.4,24.2C-13.9,18.4,-14.2,13.4,-17.6,9.5C-21.1,5.6,-27.7,2.8,-29.1,-0.8C-30.5,-4.4,-26.7,-8.8,-22.1,-10.7C-17.4,-12.5,-11.9,-11.8,-8.1,-17.1C-4.3,-22.3,-2.1,-33.4,2.8,-38.2C7.7,-43.1,15.5,-41.6,17.5,-35.4Z" width="100%" height="100%" transform="translate(50 50)" stroke-width="0" style="transition: all 0.3s ease 0s;"></path>              </svg>
  </div>
  
</template>

<script>
export default {
    name:'FormaStrana',
    data(){return{
        sfondoDx: require('../assets/images/artist-shape-01.png')
    }}
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';
div{
    height: 200px;
}
svg{
    @include centered;
    height: 100%;
    filter: brightness(0) saturate(100%) invert(55%) sepia(78%) saturate(2354%) hue-rotate(198deg) brightness(108%) contrast(98%);
}
    
</style>