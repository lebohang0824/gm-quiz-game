<template>
    <div v-if="visible" id="quiz-user">
        <h3>Hey! {{ username }} enjoy!!!</h3>
    </div>
</template>

<script>
export default {
    name: 'QuizUser',
    props: ['visible', 'username']
}
</script>

<style scoped>
    #quiz-user {
        padding: 20px 10px;
        border-radius: 5px;
        text-align: center;
        margin-block: 20px;
        background-color: #F9F7F8;
        border: solid 1px #F0F2F3;
    }
    h3 {
        color: rgba(20, 150, 74, 0.9);
    }
</style>
