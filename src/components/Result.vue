<template>
    <p>
        Reaction Time - {{score}}ms
    </p>
    <p class="result">
        {{rank}}
    </p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if(this.score < 200){
            this.rank = 'God Level.'
        } else if(this.score < 250){
            this.rank = 'Ninja Fingers!'
        } else if(this.score < 400){
            this.rank = 'Rapid Reflexes'
        } else {
            this.rank = 'Snail Pace...'
        }
    }
}
</script>

<style>
    .result {
        font-size: 1.4em;
        color: #0faf87;
        font-weight: bold;
    }
</style>