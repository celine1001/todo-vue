<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem">
        <button v-on:click="addTodo" class="btn_add">추가</button>
        
        <modal v-if="showModal" @close="showModal = false">
            <h3 slot="header">경고</h3>
            <span slot="footer" @click="showModal = false">
                할 일을 입력하세요.
                <i class="closeModalBtn fas fa-times" aria-hidden="true"></i>
            </span>
        </modal>
    </div>
</template>

<script>
    import Modal from './common/Modal.vue'
    export default{
        data(){
            return {
                newTodoItem:'',
                showModal:false
            }
        },
        methods:{
            addTodo(){
                if( this.newTodoItem !== '' ){
                    var value = this.newTodoItem && this.newTodoItem.trim();
                    this.$emit('addTodoAdd',value);
                    this.clearInput();
                }else{
                    this.showModal = !this.showModal;
                }
            },
            clearInput(){
                this.newTodoItem = '';
            }
        },
        components:{
            Modal : Modal
        }
    }
</script>

<style scoped>
    input[type="text"]{padding:5px 15px;border:1px solid #ccc;height:20px;}
    button.btn_add{height:32px;background:#000;color:#fff;border:none;width:60px;}
</style>