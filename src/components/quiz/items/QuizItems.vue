<template>
    <div v-if="visible" id="quiz-items">
        <QuizItem @submit="nextQuestion" :quiz="quizzes[questionCount]" />
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
        nextQuestion: function () {
            if (this.questionCount == 14) return alert('Done');
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
