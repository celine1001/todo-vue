<template>
    <section>
        <ul>
            <li v-for="(todoItem,index) in propsdata" :key="todoItem">
                {{todoItem}}
                <span class="removeBtn" type="button" @click="removeTodo(todoItem,index)">삭제</span>
            </li>
        </ul>
    </section>
</template>

<script>
    export default{
        props:['propsdata'],
        methods:{
            removeTodo(todoItem,index){
                localStorage.removeItem(todoItem);
                this.propsdata.splice(index,1);
            }
        }
    }
</script>

<style scoped>
    ul{list-style-type:none;}
    li{position:relative;line-height:30px;text-align:left;background:#fff;margin-top:5px;}
    li:first-child{margin-top:0;}
    .removeBtn{position:absolute;top:0;right:0;}
</style>