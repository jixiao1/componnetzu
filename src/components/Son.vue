<template>
  <div class="son">
    <h1>son组件</h1>
    <div>标题: {{title}}</div>
    <div>class: {{className}}</div>
    <div>id:{{id}}</div>
    <div>选中的是：{{seLECTed}}</div>
    <ul class="navs">
      <li>
        <button v-for="(item,index) in navs" :key="index" @click="clickHandler(item)">{{item}}</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    className: String,
    id: String,
    seLECTed: {
      type: String,
      default: '没有选中'
    }
  },
  data () {
    return {
      navs: ['A', 'B', 'C', 'D'],
      select: ''
    }
  },
  methods: {
    clickHandler (item) {
      this.select = item
      this.$emit('changer', this.select)
    }
  }
}
</script>

<style scoped>
.son {
  padding: 10px;
  border: 5px solid pink;
}
</style>
