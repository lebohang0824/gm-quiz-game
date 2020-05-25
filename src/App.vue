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
</style>
