<template>
  <div>
      <div class="sx">
                  <img :src="mySource" alt="quote">
                  <h2>I coach and mentor visual artists, like you, to Create Like You Mean It</h2>
                  <div class="sign">Martin Garrix</div>
              </div>
              <div class="dx">
                  <p>As a coach and mentor, my ultimate goal is to motivate visual artists toward inspired action. I help you get you back on track to being the productive, creative, meaningful and authentic artist you truly want to be. I support artists in crafting and living a creative life as well as feeling good about themselves and their art.</p>
                  <p>As an artist and an educator for nearly 30 years, I understand what it takes to create.</p>
                  <a role="button" href="#">Get started today</a>
              </div>
  </div>
</template>

<script>
export default {
    name: 'FirstSectionQuote',
    props: ['mySource']
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';
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
</style>