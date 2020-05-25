<template>
    <div id="app">
        <Quiz />
    </div>
</template>

<script>
import Quiz from './components/quiz/Quiz'

export default {
  name: 'App',
    components: {
        Quiz
    }
}
</script>

<style>
    body, h1, h2, h3, h4, h5, h6, p {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #2c3e50;
        padding: 0;
        margin: 0;
    }
    #app {
        padding: 0;
        margin: 0;
    }
    .btn {
        background-color: rgba(4, 12, 117, 0.6);
        border: solid 1px rgba(4, 12, 117, 0.1);
        border-radius: 5px;
        padding: 10px 0px;
        cursor: pointer;
        font-size: 20px;
        display: block;
        color: #FFF;
        width: 100%
    }
    .btn:hover {
        background-color: rgba(4, 12, 117, 0.7);
    }
    .btn:active {
        border: solid 1px rgba(4, 12, 117, 0.1);
        outline: none;
    }
    .btn:focus {
        border: solid 1px rgba(4, 12, 117, 0.1);
        outline: none;
    }
</style>
