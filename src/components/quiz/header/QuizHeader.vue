<template>
    <div id="quiz">
        <h1>Header</h1>
        <QuizDescription />
    </div>
</template>

<script>
import QuizDescription from './QuizDescription';
export default {
    name: 'QuizHeader',
    components: {
        QuizDescription
    },
    props: {
    }
}
</script>

<style scoped>
    #quiz-header {
    }
</style>
