<style>
  * {bax-sizing: border-box}
  .input {
    border:none;width:75%;height:35px;padding:10px;
    float:left;font-size:16px
  }
  .addbutton {
    padding:10px;width:25%;height:35px;background:#d9d9d9;
    color:#555;float:left;text-align:center;
    font-size:13px;cursor:pointer;transition:.3s
  }
  .addbutton:hover {background-color:#bbb}
</style>

<template>
  <div>
    <input type="text" id="task" class="input" v-model.trim="todo" placeholder="입력 후 엔터!!" v-on:keyup.enter="addTodo">
    <span class="addbutton v-on:click=addTodo">추 가</span>
  </div>
</template>

<script type="text/javascript">
  import eventBus from './EventBus.vue'

  export default {
    name: 'input-todo',
    data: function () {
      return {todo: ''}
    },
    methods: {
      addTodo: function () {
        eventBus.$emit('add-todo', this.todo);
        this.todo = '';
      }
    }
  }
</script>
