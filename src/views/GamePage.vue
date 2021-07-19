<template>
    <div>
        <h1 v-if="loginToken == undefined">ERROR user not logged in</h1>
        <div v-else></div>
        <div>
            <h1>Game Page</h1>
            <score-board></score-board>
            <user-selection></user-selection>
            <computer-selection></computer-selection>
            <div>
                <!-- name of update, move -->
                <button @click="$store.commit('playerSelection', 'rock')">Rock</button>
                <button @click="$store.commit('playerSelection', 'paper')">Paper</button>
                <button @click="$store.commit('playerSelection', 'scissors')">Scissors</button>
            </div>

        </div>
    </div>
</template>

<script>
import cookies from "vue-cookies"
import ScoreBoard from '../components/ScoreBoard.vue'
import UserSelection from '../components/UserSelection.vue'
import ComputerSelection from '../components/ComputerSelection.vue'
export default {
    components: {
        ScoreBoard,
        UserSelection,
        ComputerSelection
    },
        data() {
            return {
                loginToken: cookies.get("loginToken")
            }
        },
        
    };
</script>

<style scoped>

</style>