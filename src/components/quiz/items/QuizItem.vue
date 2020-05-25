<template>
    <div id="quiz-item">
        <div v-html="quiz.question" class="quiz-question"></div>
        <div class="quiz-answer">
            <ul v-for="answer in answers" :key="answer">
                <li class="btn-answer"  @click="submitAnswer(answer)" v-html="answer" ></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'QuizItem',
    props: ['quiz'],
    computed: {
        answers: function () {
            return [...this.quiz.incorrect_answers, this.quiz.correct_answer].sort(() => Math.random() - 0.5)
        }
    },
    methods: {
        submitAnswer: function (value) {
            this.$emit('submit', value);
        }
    }
}
</script>

<style scoped>
    #quiz-item {
        padding: 20px;
    }
    .quiz-answer ul {
        display: inline-block;
        padding: 20px 0;
        margin: 0;
    }
    .btn-answer {
        background-color: rgba(4, 12, 117, 0.6);
        border: solid 1px rgba(4, 12, 117, 0.1);
        border-radius: 4px;
        text-align: center;
        margin-right: 5px;
        padding: 10px 10px;
        list-style: none;
        min-width: 50px;
        cursor: pointer;
        color: #FFF;
    }
    .btn-answer:hover {
        background-color: rgba(4, 12, 117, 0.7);
    }
    .btn-answer:active {
        border: solid 1px rgba(4, 12, 117, 0.1);
        outline: none;
    }
    .btn-answer:focus {
        border: solid 1px rgba(4, 12, 117, 0.1);
        outline: none;
    }
</style>
