<template>
    <section>
        <transition-group name="list" tag="ul">
            <li v-for="(todoItem,index) in propsdata" :key="todoItem" class="shadow">
                {{todoItem}}
                <span class="removeBtn" type="button" @click="removeTodo(todoItem,index)">삭제</span>
            </li>
        </transition-group>
    </section>
</template>

<script>
    export default{
        props:['propsdata'],
        methods:{
            removeTodo(todoItem,index){
                this.$emit('removeTodo', todoItem, index);
            }
        }
    }
</script>

<style scoped>
    ul{list-style-type:none;}
    li{position:relative;line-height:30px;text-align:left;background:#fff;margin-top:5px;}
    li:first-child{margin-top:0;}
    .removeBtn{position:absolute;top:0;right:0;}
    
    .list-enter-active, .list-leave-active{transition: all 1s;}
    .list-enter, .list-leave-to{opacity:0;transform:translateY(30px);}
</style>




