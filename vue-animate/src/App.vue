<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Vue Animation</h1>
    <Todo />
    <Gsap />
    <GsapStagger />
    <GsapTween />
    <GsapTimeline />
    <GsapSequence />
  </div>
</template>

<script>
import Todo from './components/Todo.vue'
import Gsap from './components/Gsap.vue'
import GsapStagger from './components/GsapStagger.vue'
import GsapTween from './components/GsapTween.vue'
import GsapTimeline from './components/GsapTimeline.vue'
import GsapSequence from './components/GsapSequence.vue'

export default {
  name: 'App',
  components: {
    Todo,
    Gsap,
    GsapStagger,
    GsapTween,
    GsapTimeline,
    GsapSequence
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.list-enter-active, .list-leave-active {
  transition: all 1s;
}
.list-enter {
  opacity: 0;
  transform: translateY(30px);
}
/* -move serve per animare l'elemento selezionato dopo un evento come il sort in questo caso */
.list-move {
  transition: transform 1s ease;
}
h3 {
  margin: 60px 0;
}
</style>
