<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        Click me!
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: 0,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit('endGame', this.reactionTime)
        }
    }
}
</script>

<style>
    .block {
        width: 90%;
        max-width: 400px;
        background: #0faf87;
        color: #fff;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
        border-radius: 20px;
    }
</style>