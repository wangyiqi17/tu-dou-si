<template>
  <div>
    <button @click="changeFn">换肤</button>
    <div class="todoapp">
      <todo-header></todo-header>
      <todo-main></todo-main>
      <todo-footer></todo-footer>
    </div>
  </div>
</template>

<script>
import TodoFooter from './components/TodoFooter.vue' // shift + alt + 下
import TodoHeader from './components/TodoHeader.vue' // shift + alt + 下
import TodoMain from './components/TodoMain.vue' // shift + alt + 下

import {createNamespacedHelpers} from 'vuex'
const {mapActions:changecolor} = createNamespacedHelpers('change') 
export default {
  data() {
    return {}
  },

  components: {
    TodoFooter,
    TodoHeader,
    TodoMain,
  },

  computed: {
    
  },
  created() {},

  methods: {
    changeFn() {
      const index = Math.floor(Math.random(0,1) * 5)
      this.changeActionFn(index)
    },
    ...changecolor(['changeActionFn'])
  },
}
</script>

<style scoped></style>
