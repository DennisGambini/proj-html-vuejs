<template>
    <footer>
        <footer-top/>
        <footer-bottom/>
    </footer>
</template>

<script>
import FooterTop from './FooterTop.vue'
import FooterBottom from './FooterBottom.vue'

export default {
  components: { 
      FooterTop, 
      FooterBottom
      },
    name: 'AppFooter'
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

</style>