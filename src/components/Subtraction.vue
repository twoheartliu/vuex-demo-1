<template>
  <div>
    <div>{{ showNum }}</div>
    <button @click="sub">-1</button>
    <button @click="subN(3)">-3</button>
    <button @click="subAsync">-1 async</button>
    <button @click="subNAsync(3)">-3 async</button>
  </div>
</template>
<script>
import { mapState, mapMutations, mapActions, mapGetters } from 'vuex'
export default {
  data() {
    return {}
  },
  computed: {
    ...mapState(['count']),
    ...mapGetters(['showNum'])
  },
  methods: {
    ...mapMutations(['sub', 'subN']),
    ...mapActions(['subAsync', 'subNAsync'])
  }
}
</script>
