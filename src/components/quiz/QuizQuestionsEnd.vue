<template>
    <div v-if="visible" id="quiz-user">
        <h3>{{ username }}, you scored {{ points }} points!</h3>
        <div class="restart">
            <button @click="restart" class="btn">Start over</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'QuizQuestionsEnd',
    props: ['visible', 'username', 'points'],
    methods: {
        restart: function () {
            window.location.href = "/";
        }
    }
}
</script>

<style scoped>
    #quiz-user {
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        position: fixed;
        border-radius: 5px;
        margin-bottom: 5px;
        text-align: center;
        padding: 100px 10px;
        box-sizing: border-box;
        background-color: rgba(0, 0, 0, .9);
    }
    h3 {
        color: #FFF;
    }
    .restart {
        width: 200px;
        padding: 1px;
        margin: 20px auto;
        border-radius: 5px;
        background-color: #F0F0F0;
    }
</style>
