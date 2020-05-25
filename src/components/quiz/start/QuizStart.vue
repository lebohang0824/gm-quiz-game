<template>
    <div id="quiz-start" v-if="showStart">
        <h2>Start Quiz</h2>
        <QuizStartForm @setname="setname" />
    </div>
</template>

<script>
import QuizStartForm from './QuizStartForm';
export default {
    name: 'QuizStart',
    components: {
        QuizStartForm
    },
    data() {
        return {
            showStart: true,
        }
    },
    methods: {
        setname: function(name, quizzes) {
            this.$emit('setname', name, quizzes, true);
            this.showStart = false;
        }
    }
}
</script>

<style scoped>
    #quiz-start {
        padding: 20px;
        border-radius: 5px;
        background-color: #F9F7F8;
        border: solid 1px #F0F2F3;
    }
</style>