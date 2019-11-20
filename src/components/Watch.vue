<template>
    <div class="watch">
        <p>{{ time }}!</p>
        <button v-on:click="timerStart">{{ startBtn }}</button>
        <button v-on:click="timerStop">{{ stopBtn }}</button>
        <button v-on:click="timerReset">{{ resetBtn }}</button>
    </div>
</template>

<script>``
export default {
    name: 'Watch',
    data: function() {
        return {
            time: '00:00.000',
            startBtn: 'START',
            stopBtn: 'STOP',
            resetBtn: 'RESET'
        }
    },
    methods: {
        timerStart: function(){
            let oldTime = Date.now()
            let currentTime = Date.now() - oldTime
            console.log(currentTime)
        },
        timerStop: function() {

        },
        timerReset: function() {

        }
    }
}
</script>

<style scoped>
    .watch {
        font-size: 64px;
    }
</style>