<template>
    <div v-if="visible" id="quiz-items">
        <QuizItem @submit="nextQuestion" :quiz="quizzes[questionCount]" :questionCount="questionCount" />
    </div>
</template>

<script>
import QuizItem from './QuizItem';
export default {
    name: 'QuizItems',
    components: {
        QuizItem
    },
    props: ['visible', 'quizzes'],
    data() {
        return {
            questionCount: 0
        }
    },
    methods: {
        nextQuestion: function (value) {
            if (this.quizzes[this.questionCount].correct_answer === value) this.$emit('addPoints');
            if (this.questionCount == 14) return this.$emit('showPoints');
            this.questionCount++;
        }
    }
}
</script>

<style scoped>
    #quiz-items {
        background-color: #F9F7F8;
        border: solid 1px #F0F2F3;
    }
</style>
