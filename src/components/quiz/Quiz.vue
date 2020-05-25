<template>
    <div id="quiz">
        <QuizHeader />
        <QuizStart @setname="setname" />
        <p>{{ name }}</p>
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
    data() {
        return {
            name: null,
            quizzes: []
        }
    },
    methods: {
        setname: function(name, quizzes) {
            this.name = name;
            this.quizzes = quizzes;
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
