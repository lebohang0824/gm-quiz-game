<template>
    <div id="quiz-instructions">
        <h1>Instructions</h1>
        <p>
            This Quiz Game is crafted using <b>Vue.js</b> and <b>Trivia API</b>.<br> Answer each question
            by making selection of the correct answer provided below the question. This game has 15 questions, and 10 seconds
            to answer each question.
            All the best! <i>Show us what you got!!!</i><br>

            <a href="https://github.com/lebohang0824/gm-quiz-game">Source</a>
        </p>
        <div class="vue">
            <img src="../../../assets/logo.png" alt="Vue" />
        </div> 
    </div>
</template>

<script>

export default {
    name: 'QuizInstructions'
}
</script>

<style scoped>
    #quiz-instructions {
        padding-top: 20px;
    }
    .vue {
        width: 25px;
        height: 25px;
        padding: 8px;
        margin-top: 10px;
        border-radius: 50%;
        background-color: rgba(0, 0, 0, .1);
    }
    p {
        font-size: 14px;
    }
    img {
        padding-top: 2px;
        height: 100%;
        width: auto;
    }
</style>