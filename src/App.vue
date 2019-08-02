<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from './components/TodoFooter.vue'
export default {
    components:{
        'TodoHeader' : TodoHeader,
        'TodoInput' : TodoInput,
        'TodoList' : TodoList,
        'TodoFooter' : TodoFooter
    }
}
</script>

<style lang="scss">
    body{background:#f6f6f8;text-align:center;}
</style>
