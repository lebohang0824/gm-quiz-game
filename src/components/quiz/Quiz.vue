<template>
    <div id="quiz">
        <QuizHeader />
    </div>
</template>

<script>
import QuizHeader from './header/QuizHeader';
export default {
    name: 'Quiz',
    components: {
        QuizHeader
    },
    props: {
    }
}
</script>

<style scoped>
    #quiz {
        width: 500px;
        margin: 0 auto;
    }
</style>
