<template>
    <div>
        <h1>User Move:</h1>
        <img v-if="playerMove == 'rock'" src="@/assets/rock.png" alt="Rock Selection">
        <img v-if="playerMove == 'paper'" src="@/assets/paper.png" alt="Paper Selection">
        <img v-if="playerMove == 'scissors'" src="@/assets/scissors.png" alt="Scissors Selection">
    </div>
</template>

<script>
    export default {
        computed: {
            playerMove() {
                return this.$store.state.playMove 
            }
        },
    }
</script>

<style scoped>

</style>