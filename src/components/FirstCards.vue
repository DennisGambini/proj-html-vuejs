<template>
    <div>
        
        <!-- <div class="text">
            <div class="signature">Artist coaching</div>
            <h2>I understand what it taked to create. <br>
                    I can help you with
            </h2>
        </div> -->

        <div class="row">
            <div class="card" v-for="(card, index) in appImgs.box" :key="index">
                <img :src="appImgs.box[index].img" :alt="appImgs.box[index].title + ' img'">
                <h4>{{appImgs.box[index].title}}</h4>
                <p>{{appImgs.box[index].description}}</p>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'FirstCards',
    props:['appImgs']
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';
        .text{
            @include flex-col-between-center;
            text-align: center;
            .signature{
                @include signature-text;
            }
        }
        .row{
            @include flex-row-between;
            margin-top: $section-gap;
            gap: 40px;
            .card{
                width: calc(100% / 4);
                &:nth-of-type(2), &:nth-of-type(4){
                    position: relative;
                    top: 60px;
                }
                p{
                    color: $gray-text;
                }
            }
        }
</style>