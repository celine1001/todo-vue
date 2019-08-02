<template>
    <div>
        <input type="text" v-model="newTodoItem">
        <button v-on:click="addTodo" class="btn_add">추가</button>
    </div>
</template>

<script>
    export default{
        data(){
            return {
                newTodoItem:''
            }
        },
        methods:{
            addTodo(){
                if( this.newTodoItem !== '' ){
                    var value = this.newTodoItem && this.newTodoItem.trim();
                    localStorage.setItem(value,value);
                    this.clearInput();
                }
            },
            clearInput(){
                this.newTodoItem = '';
            }
        }
    }
</script>

<style scoped>
    input[type="text"]{padding:5px 15px;border:1px solid #ccc;height:20px;}
    button.btn_add{height:32px;background:#000;color:#fff;border:none;width:60px;}
</style>