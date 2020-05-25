<template>
    <div id="quiz-item">
        <p class="counter">{{ counter }}</p>
        <div v-html="questionCount+1+'. '+quiz.question" class="quiz-question"></div>
        <div class="quiz-answer">
            <ul v-for="answer in answers" :key="answer">
                <li class="btn-answer"  @click="submitAnswer(answer)" v-html="answer" ></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'QuizItem',
    props: ['quiz', 'questionCount'],
    data() {
        return {
            counter: 10
        }
    },
    computed: {
        answers: function () {
            return [...this.quiz.incorrect_answers, this.quiz.correct_answer].sort(() => Math.random() - 0.5)
        }
    },
    created() {
        const _self = this; 
        const countDown = setInterval(function() {
            _self.counter--;
            if (_self.counter === 0) {
                _self.submitAnswer(null);
                _self.counter = 10;
                if (_self.questionCount == 14) clearInterval(countDown);
            }
        }, 1000);
    },
    methods: {
        submitAnswer: function (value) {
            this.$emit('submit', value);
            this.counter = 10;
        }
    }
}
</script>

<style scoped>
    #quiz-item {
        padding: 20px;
        position: relative;
    }
    .quiz-answer ul {
        display: inline-block;
        padding: 20px 0;
        margin: 0;
    }
    .btn-answer {
        background-color: rgba(4, 12, 117, 0.6);
        border: solid 1px rgba(4, 12, 117, 0.1);
        border-radius: 4px;
        text-align: center;
        margin-right: 5px;
        padding: 10px 10px;
        list-style: none;
        min-width: 50px;
        cursor: pointer;
        color: #FFF;
    }
    .btn-answer:hover {
        background-color: rgba(4, 12, 117, 0.7);
    }
    .btn-answer:active {
        border: solid 1px rgba(4, 12, 117, 0.1);
        outline: none;
    }
    .btn-answer:focus {
        border: solid 1px rgba(4, 12, 117, 0.1);
        outline: none;
    }
    .counter {
        right: 5px;
        bottom: 5px;
        font-size: 15px;
        padding: 5px 8px;
        position: absolute;
        border-radius: 50%;
        color: rgb(134, 110, 0);
        background-color: rgba(221, 200, 8, 0.3);
    }
</style>
