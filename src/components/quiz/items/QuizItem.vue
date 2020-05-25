<template>
    <div id="quiz-item">
        <div @click="submitAnswer" v-html="quiz.question" class="quiz-question"></div>
        <div class="quiz-answer">
            <ul v-for="answer in answers" :key="answer">
                <li>{{ answer }}</li>
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
        submitAnswer: function () {
            this.$emit('submit');
        }
    }
}
</script>

<style scoped>
    #quiz-item {
        padding: 20px;
    }
</style>
