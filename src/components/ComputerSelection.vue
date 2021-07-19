<template>
    <div>
        <h1>Computer Move:</h1>
        <img v-if="computerMove == 'rock'" src="@/assets/rock.png" alt="Rock Selection">
        <img v-if="computerMove == 'paper'" src="@/assets/paper.png" alt="Paper Selection">
        <img v-if="computerMove == 'scissors'" src="@/assets/scissors.png" alt="Scissors Selection">
    </div>
</template>

<script>
    export default {
        computed: {
            computerMove() {
                return this.$store.state.computerMove; 
            }
        },
    }
</script>

<style scoped>

</style>