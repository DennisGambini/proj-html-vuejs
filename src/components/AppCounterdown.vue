<template>
  <section class="counter">
      <div>Starts TOMORROW! Our biggest event of the year...</div>
      <div class="clock">
          <i class="fa-regular fa-clock"></i>
          <span>00 : 00 : 00 : 00</span>
      </div>
      <button>Get ticket</button>
  </section>
</template>

<script>
export default {
    name: 'AppCounter'
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

.counter{
    @include flex-row-center-center;
    gap: 20px;
    background-color: $hint-of-red;
}

</style>