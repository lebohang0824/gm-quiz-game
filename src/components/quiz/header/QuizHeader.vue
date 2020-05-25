<template>
    <div id="quiz-header">
        <QuizInstructions />
    </div>
</template>

<script>
import QuizInstructions from './QuizInstructions';
export default {
    name: 'QuizHeader',
    components: {
        QuizInstructions
    },
    props: {
    }
}
</script>

<style scoped>
    #quiz-header {
        padding: 20px 10px;
    }
</style>
