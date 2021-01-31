<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
     <p>{{todo.title}}</p>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ["todo"]
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .todo-item {
    background: cadetblue;
    padding: 10px;
    border-bottom: 1px wheat dotted;
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background: red;
    color: white;
    border: none;
    padding: 5px 9px;
    cursor: pointer;
    float: right;
  }
  h3 {
    margin: 40px 0 0;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>
