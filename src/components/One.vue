<template>
  <div class="one">
    <input type="text" v-model="inpurw">
    <button @click="clickHandler">添加</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      inpurw: ''
    }
  },
  methods: {
    clickHandler () {
      // console.log(this.inpurw)
      this.$eventbus.$emit('go', this.inpurw)
      this.inpurw = ''
    }
  }
}
</script>

<style>

</style>
