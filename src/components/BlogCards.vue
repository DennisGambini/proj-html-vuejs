<template>
    <div class="blog-row">
        <div class="blog-card" v-for="(item, i) in myArray" :key="i">
            <img :src="myArray[i].img" :alt="myArray[i].name">
            <div class="blog-text">
                <div class="artist">{{myArray[i].artist}}</div>
                <div class="title">{{myArray[i].title}}</div>
                <div class="description">
                    <span>
                        <i class="fa-regular fa-calendar"></i>
                        {{myArray[i].description.duration}} Lessons
                    </span>
                    <span>
                        <i class="fa-regular fa-eye"></i>
                        {{myArray[i].description.views}} views
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

.blog-row{
    @include container-md;
    @include flex-row-between-center;
    padding: $section-gap 0;
    flex-wrap: wrap;
    row-gap: 50px;
    column-gap: 30px;
    .blog-card{
        background-color: $white;
        @include ombra-light;
        @include flex-col-start-start;
        &:nth-of-type(2){
            position: relative;
            img{
                width: 500px;
                filter: brightness(90%);
            }
            .blog-text{
                color: $white;
                position: absolute;
                bottom: 0;
                .artist,.title{
                    font-size: 1.3em;
                    color: $white;
                }
                .description{
                    color: $white;
                }
            }

        }
        &:last-of-type{
            align-self: flex-start;
            margin-top: 50px;
        }
        flex-basis: calc((100% / 4) - (90px / 3));
        img{
            width: 100%;
        }
        .blog-text{
            @include flex-col-between-start;
            padding: 20px;
            gap: 15px;
            flex-grow: 1;
            .artist{
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
    }
}

</style>