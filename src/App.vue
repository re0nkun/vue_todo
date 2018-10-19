<template>
<div id="app">
  <ul>
    <Item v-for="item in items" :key="item.id" :item="item"/>
  </ul>
  <div>
    <input type="text" v-model="inputTitle">
    <button @click="ADD_TASK(inputTitle)">追加</button>
  </div>
</div>
</template>

<script>
import {mapState, mapActions} from 'vuex'
import * as types from './store/mutation-types'
import Item from './Item'

export default {
  name: 'app',
  components: {'Item': Item},

  data() {
    return {
      // items: this.$store.state.items,
      inputTitle: ""
    }
  },
  computed: {
    ...mapState(['items'])
  },
  methods: {
    ...mapActions([
      types.ADD_TASK
    ])
  }
}
</script>

<style>
</style>