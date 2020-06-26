<template>
  <div class="wrapper">
    <h3>Animation group vue</h3>
    <input type="text" v-model="itemToAdd">
    <button class="button" @click="addITem">Add</button>
    <button class="button" @click="sortITem">Sort</button>
    <!-- transition group e per fare transizioni su gruppi. appear fa l'animazione anche agli item gia esistenti -->
    <transition-group name="list" tag="ul" appear>
      <li class="item" v-for="(item, i) in itemList" :key="i">
        {{item}}
      </li>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  data () {
    return {
      itemToAdd: '',
      itemList: ['test', 'test']
    }
  },
  props: {
    msg: String
  },
  methods: {
    addITem() {
      this.itemList.push(this.itemToAdd)
      this.itemToAdd = ''
    },
    sortITem () {
      this.itemList.sort()
    }
  }
}
</script>

<style scoped>
  .wrapper input {
    width: 50%;
      margin-right: 30px;
      margin-bottom: 30px;
      height: 1.5rem;
      border-radius: 5px;
  }
  .button {
    width: 200px;
    height: 1.9rem;
    border-radius: 5px;
    background-color: #2d2d2d;
    color: #fff;
  }
  .item {
    list-style: none;
    font-size: 17px;
    margin-bottom: 5px;
  }
</style>
