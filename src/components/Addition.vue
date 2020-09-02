<template>
  <div>
    <!-- <div>当前最新的count值为：{{ $store.state.count }}</div> -->
    <div>{{ $store.getters.showNum }}</div>
    <button @click="handleBtnAdd">+1</button>
    <button @click="handleBtnAddN">+3</button>
    <button @click="handleBtnAddAsync">+1 async</button>
    <button @click="handleBtnAddNAsync">+3 async</button>
  </div>
</template>
<script>
export default {
  data() {
    return {}
  },
  methods: {
    handleBtnAdd() {
      // 1. vue 中不可直接操作 store 中的数据
      // 2. vue 中必须使用 mutation 来操作数据，mutation 可以集中监控所有数据的变化
      // 3. 直接操作 store 会导致后期无法查找是哪里改变了 store 的值
      // this.$store.state.count++;
      // 使用 $store.commit 调用在 store 的 mutations 中定义好的函数
      this.$store.commit('add')
    },
    handleBtnAddN() {
      this.$store.commit('addN', 3)
    },
    handleBtnAddAsync() {
      this.$store.dispatch('addAsync')
    },
    handleBtnAddNAsync() {
      this.$store.dispatch('addNAsync', 3)
    }
  }
}
</script>
