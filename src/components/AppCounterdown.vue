<template>
    <section class="counter">
        <div>Starts TOMORROW! Our biggest event of the year...</div>

        <div class="clock">
            <i class="fa-regular fa-clock"></i>
            <span>00 : </span>
            <span class="time">{{fill(reverseHour(hour)) + ' : '}}</span>
            <span class="minute">{{fill(reverseMin(minute)) + ' : '}}</span>
            <span class="seconds">{{fill(reverseSec(second))}}</span>
        </div>

        <a href="#">Get ticket</a>
    </section>
</template>

<script>
export default {
    name: 'AppCounter',
    data(){return{
        hour: '',
        minute: '',
        second: ''
    }},
    methods:{
        fill(number){
            if(number < 10){
                return `0${number}`
            } else {
                return number
            }
        },
        reverseHour(hour){
            return 23 - hour
        },
        reverseMin(min){
            return 59 - min
        },
        reverseSec(seconds){
            return 59 - seconds
        }
    },
    mounted(){
        setInterval(() => {
            const date = new Date()
            const hour = date.getHours()
            const minutes = date.getMinutes()
            const seconds = date.getSeconds()
            this.hour = hour
            this.minute = minutes
            this.second = seconds
            console.log(this.second)
        }, 1000);
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

.counter{
    @include flex-row-center-center;
    height: 50px;
    gap: 30px;
    background-color: $my-silver;
}
a{
    @include orange-sm-btn;
}
.clock{
    font-weight: 600;
    min-width: 155px;
    i{
        margin-right: 20px;
    }
}

</style>