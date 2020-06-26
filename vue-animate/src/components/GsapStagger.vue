<template>
  <div>
    <h3>Gsap vue Stagger</h3>
    <div class="wrapper-stagger">
      <div v-for="card in cards" :key="card.id" class="card-stagger"></div>
    </div>
  </div>
</template>

<script>
import gsap from 'gsap';
export default {
  name: 'GsapStagger',
  data () {
    return {
      cards: [
        {id: 1234},
        {id: 1264},
        {id: 1534},
        {id: 1964},
        {id: 1324},
        {id: 1644},
      ]
    }
  },
  mounted () {
    gsap.from('.card-stagger', {
      duration: 0.5,
      opacity: 0,
      scale: 0,
      y: 200,
      ease: 'power1',
      // stagger crea un ritardo tra un'animazione ed un'altra
      stagger: {
        each: 0.1,
        from: 'edges'
      },
    })
  },
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
  .wrapper-stagger {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    grid-gap: 20px;
  }
  .card-stagger {
    width: 100%;
    height: auto;
    min-height: 200px;
    background-color: #41B87D;
    border-radius: 10px;
    display: block;
    margin: 0 auto;
  }
</style>
