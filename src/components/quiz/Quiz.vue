<template>
    <div id="quiz">
        <QuizHeader />
        <QuizStart @setname="setname" />
        <QuizUser :username="name" :visible="visible" />
        <QuizItems :quizzes="quizzes" :visible="visible" />
    </div>
</template>

<script>
import QuizHeader from './header/QuizHeader';
import QuizStart from './start/QuizStart';
import QuizUser from './QuizUser';
import QuizItems from './items/QuizItems';
export default {
    name: 'Quiz',
    components: {
        QuizHeader,
        QuizStart,
        QuizUser,
        QuizItems
    },
    data() {
        return {
            name: null,
            quizzes: [],
            visible: false
        }
    },
    methods: {
        setname: function(name, quizzes, visible) {
            this.name = name;
            this.quizzes = quizzes;
            this.visible = visible;
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
