<template>
  <div id="app">
   <Father></Father>
   <ONE/>
   <Two></Two>
   <ul class="navs1">
     <li v-for="(item,index) in list"
     :key="item" :class="index === activeIndsex ? 'active' : ''"
     @click="clickHandler(index)">{{item}}</li>
   </ul>
   <!-- <one v-if="activeIndsex === 0"></one>
   <two v-if="activeIndsex === 1" ></two>
   <three v-if="activeIndsex === 2"></three> -->
   <keep-alive>
     <component :is="comName"></component>
   </keep-alive>
  </div>
</template>

<script>
import Father from '@/components/Father.vue'
import ONE from '@/components/One.vue'
import Two from '@/components/Two.vue'
import one from '@/pages/One.vue'
import two from '@/pages/Two.vue'
import three from '@/pages/Three.vue'
export default {
  name: 'App',
  data: function () {
    return {
      list: ['one', 'two', 'three'],
      activeIndsex: 0
    }
  },
  components: {
    // HelloWorld
    Father,
    ONE,
    Two,
    one,
    two,
    three
  },
  computed: {
    comName () {
      let swr = ''
      switch (this.activeIndsex) {
        case 0:
          swr = 'one'
          break
        case 1:
          swr = 'two'
          break
        case 2:
          swr = 'three'
      }
      return swr
    }
  },
  methods: {
    clickHandler (index) {
      this.activeIndsex = index
      console.log(index)
    }
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
.navs1 {
  width: 100%;
  height: 60px;
  display: flex;
  list-style: none;
}
.navs1 li {
    flex: 1;
    height: 60px;
    background-color: #333;
    color: white;
    line-height: 60px;
    text-align: center;
   border-right: 1px solid white;
  }
  .navs1 li.active {
    background-color: yellowgreen;
  }
</style>
