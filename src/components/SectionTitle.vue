<template>
    <div class="text">
        <div class="signature">{{signature}}</div>
        <h2>{{text}}</h2>
    </div>
</template>

<script>
export default {
    name: 'SectionTitle',
    props:{
        signature: String,
        text: String
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';
    .text{
        @include flex-col-between-center;
        margin: 0 auto;
        width: 30%;
        .signature{
            @include signature-text;
            font-weight: 600;
            font-size: $huge-text;
        }
        h2{
            font-size: $xl-text;
            font-weight: 700;
        }
}

</style>