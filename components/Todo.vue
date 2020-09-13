<template>
  <div class='todo'>
    <form class='todo-form' @submit.prevent='add'>
      <input v-model='current'> <input type='submit' value='Add'>
    </form>
    <ol class='todos'>
      <li
        v-for='(todo, index) in todos'
        :key='todo.id'
        >
          {{ todo.text }} <input type='button' value='Remove' @click='remove(index)'>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
methods: {
  add: function(){
       console.log(this.current);
       this.todos.push({
         id: this.nextTodo++,
         text: this.current
       });
  },
  remove: function(index){
        this.todos.splice(index, 1);
  }
},
data: function(){ 
  return {
    current: '',
    nextTodo: 0,
    todos: []
        }
  }
}
</script>

<style>
.todo-form{
  padding: .5em 0;
  display: flex;
  flex: 1 1 auto;
  flex-flow: row;
}
input{
  padding: .5em 1em;
  border-radius: 0;
  border: 0;
  border-bottom: .3em solid var(--theme);
  border-right: .3em solid var(--theme);
  margin-right: 1em;
  background: var(--contrast);
  color: var(--background);
  transition: background .1s, color .1s;
}
input:hover{
  background: var(--theme);
  color: var(--contrast);
}
input:active{
  background: var(--theme-accent);
  color: var(--contrast);
}
.todos{
  display: flex;
  flex-flow: column;
  counter-reset: notes;
}
.todos li{
  list-style: decimal;
  display: flex;
  flex-flow: row;
  margin-top: .5em;
  justify-content: space-between;
}
.todos li:before{
  counter-increment: notes;
  content: counter(notes, decimal);
}
.todos input{
  padding: 0.1em 0.5em;
}
</style>
