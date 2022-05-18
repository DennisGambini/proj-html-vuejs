<template>
    <div class="scritta">{{scritta}}</div>
</template>

<script>
export default {
    name: 'ScrittaSfondo',
    props: {
        scritta: String
    }
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

.scritta{
            text-transform: capitalize;
            font-size: 150px;
            font-weight: 700;
            color: white;
            // QUESTO LO METTO NEL PADRE
            // position: absolute;
            // right: -10%;
            // top: 50%;
            opacity: 0.3;
            z-index: -1;
            transform: translateY(-50%) rotate(90deg);
            text-shadow: 1px 1px  rgba($color: $matrix, $alpha: 0.15),
            1px -1px rgba($matrix, 0.15),
            -1px 1px rgba($matrix, 0.15),
            -1px -1px rgba($matrix, 0.15),
            2px 2px rgba($matrix, 0.15),
            2px -2px rgba($matrix, 0.15),
            -2px 2px rgba($matrix, 0.15),
            -2px -2px rgba($matrix, 0.15),
            3px 3px rgba($matrix, 0.15),
            3px -3px rgba($matrix, 0.15),
            -3px 3px rgba($matrix, 0.15),
            -3px -3px rgba($matrix, 0.15),
    }

</style>