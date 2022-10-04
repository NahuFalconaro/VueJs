<template>
  <!-- <h2>Test {{todo}}</h2>
  <input v-bind:value="todo" v-on:input="todo = $event.target.value" > -->
  <input v-model="todo" type="text">
  <button @click="addTask(todo)">add task</button>
  <ul>
    <li v-for="t in todos" :key="t.id" v-bind:class="{'check': t.checked}"> {{t.info}}     
    <button @click="updateStatusTask(t.id)">finish task</button>
    <button @click="deleteTask(t.id)">delete task</button>
  </li>
  </ul>
  <button v-if="todos.length > 0" @click="deleteAll()">Delete All</button>
</template>

<script>
export default {
  name: 'Tasks_list',
  data(){
    return{
      initialId: 0,
      todo: '',
      todos: [],
    }
  },
   methods: {
    addTask(todo){
      this.todos.push({
        id: this.initialId++,
        info: todo,
        checked: false
      });
      this.todo = " ";
      console.log(this.todos);
    },
    updateStatusTask(id){
      //let response = this.todos.filter(e=> e.id===id);
      //si hacemos filter retorna copia con el valor.
      this.todos.map(e=>{if (e.id===id) e.checked = !e.checked})
    },
    deleteTask(id){
      this.todos = this.todos.filter(e => { return e.id !== id})
    },
    deleteAll(){
      this.todos = [];
    }
   },
   directives:{},
   //metodos directivas


}
</script>
<style>

  .check{
    color: red;
  }

</style>
