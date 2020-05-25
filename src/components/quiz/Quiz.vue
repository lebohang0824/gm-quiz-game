<template>
    <div id="quiz">
        <QuizHeader />
        <QuizStart @setname="setname" />
        <QuizUser :username="name" :visible="visible" />
        <QuizItems :quizzes="quizzes" :visible="visible" @showPoints="showPoints" @addPoints="addPoints" />
        <QuizQuestionsEnd :visible="pointsVisible" :username="name" :points="points" />
    </div>
</template>

<script>
import QuizHeader from './header/QuizHeader';
import QuizStart from './start/QuizStart';
import QuizUser from './QuizUser';
import QuizItems from './items/QuizItems';
import QuizQuestionsEnd from './QuizQuestionsEnd';
export default {
    name: 'Quiz',
    components: {
        QuizHeader,
        QuizStart,
        QuizUser,
        QuizItems,
        QuizQuestionsEnd
    },
    data() {
        return {
            points: 0,
            name: null,
            quizzes: [],
            visible: false,
            pointsVisible: false
        }
    },
    methods: {
        setname: function(name, quizzes, visible) {
            this.name = name;
            this.quizzes = quizzes;
            this.visible = visible;
        },
        showPoints: function () {
            this.pointsVisible = true;
        },
        addPoints: function () {
            this.points += 10;      
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
