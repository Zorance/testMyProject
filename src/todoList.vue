<template>
  <div id="app">
     <input v-model="val" />
     <button @click="submitItem">提交</button>
     <ul>
        <todo-items 
          v-for="(item,index) of list" 
          :key="index"
          :content="item"
          :index="index"
          @remove="remove">
        </todo-items>
     </ul>
  </div>
</template>

<script>
import toDoItems from './components/toDoItems'

export default {
  components:{
      'todo-items':toDoItems
  },
  data(){
    return {
        val:'',
        list:[]
    }
  },
  methods:{
    submitItem(){
      this.list.push(this.val);
      this.val='';
    },
    remove(index){
      this.list.splice(index,1);
    }
  }
}
</script>

<style>


</style>
