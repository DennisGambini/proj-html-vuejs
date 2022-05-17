<template>
    <div class="carousel">
        <div class="carousel-row">
            <div class="carousel-card" v-for="(item, i) in 3" :key="i" :class="i === 1 ? 'active' : 'non-active'">
                <div class="title">{{myArray[swap(counter + i)].title}}</div>
                <p>{{myArray[swap(counter + i)].description}}</p>
                <div class="card-footer">
                    <img :src="myArray[swap(counter + i)].img" :alt="myArray[swap(counter + i)].name + ' ' + 'avatar'">
                    <div class="author">
                        <div class="name">{{myArray[swap(counter + i)].name}}</div>
                        <div class="job">{{myArray[swap(counter + i)].job}}</div>
                    </div>
                </div>
            </div>
        </div>
        <div class="dots">
            <i class="fa-solid fa-circle" v-for="(n, i) in 4" :key="i" :class="i === counter ? 'i-active' : 'i-nonactive' "></i>
        </div>
    </div>
</template>

<script>

export default {
    name: 'AppCarousel',
    props:{
        myArray: Array
    },
    data(){return{
        counter: 0
    }},
    methods:{
        swap(n){
            if(n === this.myArray.length){
                return 0
            } else if (n === this.myArray.length + 1) {
                return 1
            } else {
                return n
            }
        }
    },
    mounted(){
        setInterval(()=>{
            if(this.counter === 3){
                this.counter = 0;
            } else {
                this.counter ++
            }
        }, 2000)

    }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

.carousel{
    // background: green;
    padding: $section-gap 0;
}
.carousel-row{
    width: 95%;
    margin: 0 auto;
    margin-bottom: 30px;
    @include flex-row-between-center;
    gap: 20px;
    flex-wrap: wrap;
    .carousel-card{
        min-height: 300px;
        @include flex-col-around-start;
        flex-basis: calc((100% / 3) - (70px / 3));
        gap: 35px;
        padding: 20px;
        background-color: $white;
        .title{
            font-weight: 600;
        }
        p{
            color: $gray-text;
        }
        .card-footer{
            img{
                height: 50px;
                border-radius: 50%;
            }
            @include flex-row-start-center;
            gap: 20px;
        }
    }

    .active{
        opacity: 1;
    }
    .non-active{
        opacity: 0.3;
    }
}

.dots{
    text-align: center;
    i{
        vertical-align: middle;
        margin: 0 7px;
    }
    .i-active{
        font-size: 12px;
        color: $primary-text;
    }
    .i-nonactive{
        font-size: 8px;
        color: rgba($color: $primary-text, $alpha: 0.5);
    }
}



</style>