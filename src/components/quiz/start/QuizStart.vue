<template>
    <div id="quiz-start">
        <h2>Start Quiz</h2>
        <QuizStartForm />
    </div>
</template>

<script>
import QuizStartForm from './QuizStartForm';
export default {
    name: 'QuizStart',
    components: {
        QuizStartForm
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