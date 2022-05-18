<template>
    <div class="course-row">
        <div class="course-card" v-for="(item, i) in myArray" :key="i">
            <div class="course-img">
                <img :src="myArray[i].img" :alt="myArray[i].name">
            </div>
            <div class="course-text">
                <div class="price">&dollar; {{myArray[i].price}}</div>
                <div class="title">{{myArray[i].title}}</div>
                <div class="description">
                    <span>
                        <i class="fa-solid fa-sheet-plastic"></i>
                        {{myArray[i].description.duration}} Lessons
                    </span>
                    <span>
                        <i class="fa-regular fa-user"></i>
                        {{myArray[i].description.students}} Students
                    </span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CoursesCards',
    props: ['myArray']
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

.course-row{
    @include container-md;
    @include flex-row-between-stretch;
    padding: $section-gap 0;
    flex-wrap: wrap;
    row-gap: 50px;
    column-gap: 30px;
    .course-card{
        @include flex-col-start-start;
        flex-basis: calc((100% / 4) - (90px / 3));
        cursor: pointer;
        .course-img{
            width: 255px;
            height: 255px;
            overflow: hidden;
            position: relative;
            img{
                height: 100%;
                width: 100%;
                object-fit: cover;
                object-position:right;
                transition: all 1.3s ease;
                @include centered
            }
        }
        .course-text{
            @include flex-col-between-start;
            padding: 20px;
            gap: 15px;
            flex-grow: 1;
            border: 2px solid transparent;
            width: 90%;

            .price{
                font-size: $md-text;
                color: $tulip-tree;
                font-weight: 600;
            }
            .title{
                font-size: $md-text;
                font-weight: 600;
                text-align: start;
            }
            .description{
                font-size: $sm-text;
                color: $gray-text;
                font-weight: 500;
                @include flex-row-start;
                gap: 20px;
            }
            transition: all 0.3s;
            position: relative;
            top: 0;
        }
        &:hover{
            .course-text{
                background-color: $white;
                border: 2px solid $thunderbird;
                position: relative;
                top: -30px;
            }
            img{
                height: 120%;
                width: 120%;
            }
        }
    }
}

</style>