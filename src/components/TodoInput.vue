<template>
    <div class="inputBox shadow">
      <input type="text" v-model="newTodoItem" v-on:keypress.enter="addTodo">
      <span class="addContainer" v-on:click="addTodo">
      <i class="addBtn fas fa-plus addBtn" aria-hidden="true"></i>
    </span>

      <modal v-if="showModal" @close="showModal = false">
        <h3 slot="header">
          경고!
          <i class="closeModalBtn fas fa-times" aria-hidden="true" @click="showModal=false"></i>
        </h3>
        <span slot="body" @click="showModal = false">할 일을 입력하세요.

      </span>
      </modal>
    </div>
</template>

<script>
    import Modal from "./common/Modal.vue";

    export default {
      data(){
        return{
          newTodoItem:'',
          showModal: false,
        }
      },
      methods:{
        addTodo(){
          if(this.newTodoItem !== ''){
            //this.$emit('addTodoItem',this.newTodoItem);
            //뮤테이션은 commit으로 동작시킨다.
            this.$store.commit('addOneItem', this.newTodoItem);
            this.clearInput();
          }else{
            this.showModal = !this.showModal;
          }
        },
        clearInput(){
          this.newTodoItem = '';
        },
      },
      components:{
        Modal
      },
    }
</script>

<style scoped>
  input:focus {
    outline: none;
  }
  .inputBox {
    background: white;
    height: 50px;
    line-height: 50px;
    border-radius: 5px;
  }
  .inputBox input {
    border-style: none;
    font-size: 0.9rem;
  }
  .addContainer {
    float: right;
    background: linear-gradient(to right, #6478FB, #8763FB);
    display: inline-block;
    width: 3rem;
    border-radius: 0 5px 5px 0;
  }
  .addBtn {
    color: white;
    vertical-align: middle;
  }
  .closeModalBtn{
    color:#42b983;
  }
</style>
