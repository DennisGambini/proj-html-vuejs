<template>
    <div class="event-row">
        <div class="event-card" v-for="(item, i) in myArray" :key="i">
            <div class="img">
                <img :src="myArray[i].img" :alt="myArray[i].title">
            </div>
            <div class="event-text">
                <div class="date">{{myArray[i].date}}</div>
                <div class="title">{{myArray[i].title}}</div>
                <div class="description">
                    <span>
                        <i class="fa-solid fa-location-dot"></i>
                        {{myArray[i].place}}
                    </span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BlogCards',
    props: ['myArray']
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

.event-row{
    @include flex-row-between-stretch;
    padding: $section-gap 0;
    flex-wrap: wrap;
    row-gap: 50px;
    column-gap: 50px;
    .event-card{
        @include flex-row-start-stretch;
        flex-basis: calc((100% / 2) - 25px);
        .img{
            height: 300px;
            img{
                height: 100%;
                width: 100%;
                object-fit: cover;
                object-position: center;
            }
        }
        .event-text{
            @include flex-col-center-start;
            padding: 40px;
            gap: 15px;
            flex-grow: 1;
            .date{
                font-size: $md-text;
                color: $gray-text;
                text-transform: uppercase;
                font-weight: 600;
            }
            .title{
                font-size: $md-text;
                font-weight: 600;
            }
            .description{
                font-size: $sm-text;
                color: $gray-text;
                font-weight: 500;
                @include flex-col-start;
                gap: 20px;
            }
        }
        &:nth-of-type(3), &:nth-of-type(4){
            flex-direction: row-reverse;
            .event-text{
                align-items: flex-end;
            }
        }
    }
}

</style>