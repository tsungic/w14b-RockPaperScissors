<template>
    <div>
        <h1>Wins: {{ wins }}</h1>
        <h1>Losses: {{ losses }}</h1>
        <h1>Ties: {{ ties }} </h1>
    </div>
</template>

<script>
    export default {
    computed: {
        wins() {
            return this.$store.state.wins 
        },
        losses() {
            return this.$store.state.losses
        },
        ties() {
            return this.$store.state.ties
        }
    },
        
}
</script>

<style scoped>

</style>