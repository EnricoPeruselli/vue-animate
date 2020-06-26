<template>
  <div class="wrapper">
    <h3>Gsap vue simple animation</h3>
    <transition @before-enter="beforeEnter" @enter="enter" :css="false" appear>
      <div class="card"></div>
    </transition>
  </div>
</template>

<script>
import gsap from 'gsap';
export default {
  name: 'Gsap',
  methods: {
    beforeEnter(el) {
      el.style.opacity = 0
      el.style.transform = 'scale(0,0)'
    },
    enter (el, done) {
      gsap.to(el, {
        duration: 1,
        opacity: 1,
        scale: 1,
        ease: 'bounce.out',
        // onComplete fa una callback e done fa andare al passo successivo del lifecycle
        onComplete: done
      })
    }
  }
}
</script>

<style scoped>
  .card {
    width: 200px;
    height: 200px;
    background-color: #41B87D;
    border-radius: 10px;
    display: block;
    margin: 0 auto;
  }
</style>
