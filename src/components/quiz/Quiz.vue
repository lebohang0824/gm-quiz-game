<template>
    <div id="quiz">
        <QuizHeader />
        <QuizStart />
        <p v-bind:bind="store"></p>
    </div>
</template>

<script>
import QuizHeader from './header/QuizHeader';
import QuizStart from './start/QuizStart';
export default {
    name: 'Quiz',
    components: {
        QuizHeader,
        QuizStart
    },
    props: {
        store: {
            user: 'Lebohang'
        }
    }
}
</script>

<style scoped>
    #quiz {
        width: 500px;
        margin: 0 auto;
    }
</style>
