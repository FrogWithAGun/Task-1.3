<script setup>
    import {ref} from 'vue';

    const score = ref(0);
    const highScore = ref(0);

    // A function that increases the value of the score and high score variables.
    const increaseScore = () => {
        score.value++;

        if (score.value > highScore.value) {
            highScore.value = score.value;
        }
    }

    // A function that resests the score variable to 0
    const resetScore = () => {
        score.value = 0;
    }

    // Set interval is used to execute the resetScore() function every 10 seconds.
    setInterval(resetScore, 10000);
</script>

<template>
    <div class="button-game">
        <div class="section-title">
            <h2>Here is a game for you to play if you are bored.</h2>
        </div>
        
        <div class="text-container">
            <p>Click the button to increase you're score by 1. You're score will reset every 10 seconds.<br>Try and see what the highest score you can get is.</p>
        </div>

        <br>

        <div class="game-container">
            <div class="button-container">
                <button @click="increaseScore" class="nice-button">Click Here</button>
            </div>

            <div class="score-container">
                <p>Score: {{ score }}</p>
                <p>High Score: {{ highScore }}</p>
            </div>
        </div>
    </div>
</template>