<template>
<!-- 一个模版里只能有一个根标签 -->
  <div id="app">
    <h1>todolist</h1>
    <div>
    <input v-model="inputValue"/>
    <button @click="handleSubmit">提交</button>
    </div>
    <ul>
      <todo-item  v-for="(item,index) of list"  
      :key="index" 
      :itemContent="item"
      :index="index"
      @delete='handleDelete'>
      </todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'
export default {
  components:{
    'todo-item': TodoItem //注册局部组件，使用todo-item的标签 来使用引入的组件
  },
  //注意差别，data变成了一个函数
  data: function(){
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit: function(){
      this.list.push(this.inputValue)
      inputValue = ''
},
    handleDelete: function(index){
      this.list.splice(index,1)
    }
  }
}
</script>

<style>

</style>
