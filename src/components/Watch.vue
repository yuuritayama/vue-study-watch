<template>
    <div class="watch">
        <p>{{ time }}</p>
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
            time: '0',
            savedTime: '0',
            startBtn: 'START',
            stopBtn: 'STOP',
            resetBtn: 'RESET',
            started: false,
            timerId: undefined
        }
    },
    methods: {
        // startBtnが押されたときの処理
        timerStart: function(){
            console.log(this.started)
            if (this.started === false) {
                let startTime = Date.now()
                console.log(startTime)
                let log = () => {
                    //console.log("test")      
                    this.time = Date.now() - startTime + parseInt(this.savedTime)
                    //this.time++
                    console.log(this.time)
                }
                this.timerId = setInterval(log, 1000) //clearIntervalで使うため
                this.started = true
            }
             
              
            //  console.log(countUp)
        },
        timerStop: function() {
            clearInterval(this.timerId)
            this.started = false
            this.savedTime = parseInt(this.time)
            console.log(this.savedTime)
        },
        timerReset: function() {
            //console.log("hello")
            clearInterval(this.timerId)
            this.time = 0
            this.savedTime = 0
            console.log(this.time)
        }
    }
}
</script>

<style scoped>
    .watch {
        font-size: 64px;
    }
</style>