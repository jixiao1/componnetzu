<template>
  <div class="father">
    <h1>father组件</h1>
    <ul>
      <li>
        <button v-for="item in arr" :key="item" @click="clickHandler(item)">{{item}}</button>
      </li>
    </ul>
        <div>点击子组件传给父组件的值：{{se}}</div>
    <Son title="你好，儿子" className="clqadjkfj" id="jiakka" :seLECTed="seLECTed"
    @changer ="changeer"></Son>
  </div>
</template>

<script>
import Son from '@/components/Son.vue'
export default {
  components: {
    Son
  },
  data () {
    return {
      arr: ['A', 'B', 'C', 'D'],
      seLECTed: '',
      se: ''
    }
  },
  methods: {
    clickHandler (item) {
      console.log(item)
      this.seLECTed = item
    },
    changeer (data) {
      console.log(data)
      this.se = data
    }
  }
}
</script>

<style scoped>
.father {
  padding: 20px;
  border: 5px solid #333333;
}
</style>
