<template>
  <div class="two">
    <ul>
      <li v-for="(item,index) in list" :key="index">
        {{item}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      list: []
    }
  },
  created () {
    this.$eventbus.$on('go', (data) => {
      // console.log(data)
      this.list.push(data)
    })
  }
}
</script>

<style>

</style>
