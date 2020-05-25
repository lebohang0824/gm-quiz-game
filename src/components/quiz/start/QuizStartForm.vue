<template>
    <form id="start-form" v-on:submit.prevent="onSubmit">
        <div class="group">
            <label>Name</label>
            <input type="text" class="input" placeholder="Name" />
        </div>
        <div class="group">
            <label>Difficulty</label>
            <select class="select">
                <option value="">Any</option>
                <option value="easy">Easy</option>
                <option value="medium">Medium</option>
                <option value="hard">Hard</option>
            </select>
        </div>
        <button class="btn">Start</button>
    </form>
</template>

<script>
import axios from 'axios';
export default {
    name: 'QuizStartForm',
    methods: {
        onSubmit: async (e) => {
            const name = e.target[0].value;
            const difficulty = e.target[1].value;

            console.log(name, difficulty);
            const url = `https://opentdb.com/api.php?amount=15&category=9&difficulty=${difficulty}`;

            const res = await axios.get(url);
            console.log(res.data.results);
        }
    }
    
}
</script>

<style scoped>
    #start-form {
        background-color: #F9F7F8;
    }
    .group {
        display: block;
        padding: 10px 0px;
        padding-top: 0px;
    }
    .group label {
        display: block;
        font-size: 14px;
        padding: 5px 0px;
    }
    .group .select {
        width: 100%;
        display: block;
        padding: 8px 10px;
        border-radius: 5px;
        box-sizing: border-box;
        background-color: #FFF;
        border: solid 1px rgb(57, 160, 83);
    }
    .select:focus {
        border: solid 1px rgb(57, 160, 83);
        outline: none;        
    }
    .group .input {
        width: 100%;
        display: block;
        padding: 8px 10px;
        border-radius: 5px;
        box-sizing: border-box;
        background-color: #FFF;
        border: solid 1px rgb(57, 160, 83);
    }
    .input:focus {
        border: solid 1px rgb(57, 160, 83);
        outline: none;        
    }
</style>