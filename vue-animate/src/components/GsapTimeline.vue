<template>
  <div>
    <img class="runner first" src="https://picsum.photos/200/300" alt="runner" />
    <img class="runner second" src="https://picsum.photos/200/300" alt="runner" />
    <img class="runner third" src="https://picsum.photos/200/300" alt="runner" />
  </div>
</template>

<script>
import gsap from 'gsap'

export default {
  mounted() {
    let lt = gsap.timeline({repeat: -1, repeatDelay: 1, yoyo: true})
    lt.to('.first', { x: 700, duration: 2, ease: 'expo.out' })
    lt.to('.second', { x: 700, duration: 2, ease: 'expo.out' }, '-=.75')
    // il simbolo < fa partire l'animazione allo stesso tempo della precedente
    lt.to('.third', { x: 700, duration: 2, ease: 'expo.out' }, '<')
  }
}
</script>

<style scoped>
.runner {
  display: block;
  height: 5em;
  width: 5em;
  margin-top: 1.5em;
}
</style>