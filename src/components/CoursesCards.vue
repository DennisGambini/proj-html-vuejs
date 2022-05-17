<template>
    <div class="course-row">
        <div class="course-card" v-for="(item, i) in myArray" :key="i">
            <img :src="myArray[i].img" :alt="myArray[i].name">
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
        img{
            width: 100%;
        }
        .course-text{
            @include flex-col-between-start;
            padding: 20px;
            gap: 15px;
            flex-grow: 1;
            .price{
                font-size: $md-text;
                color: $tulip-tree;
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
                @include flex-row-start;
                gap: 20px;
            }
        }
    }
}

</style>