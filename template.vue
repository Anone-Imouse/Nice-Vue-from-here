<template>
  <div id="app">
    <h1>{{message}}</h1>
<input @keyup.enter="add" type="text" v-model.trim="addinp" maxLength="15">
    <br>
    <br>
    <button @click="add">Add Todo</button>
    <button @click="clear">Clear List</button>
    <ul>
      <li v-for="todo in todos">{{todo}}<button @click="remove">Remove</button></li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'To Do List App',
      todos:['Example ToDo'],
      addinp:'',
    };
  },
  methods: {
    add(){
      if(this.addinp !== ''){
  this.todos.push(this.addinp)
    this.addinp=''
      }
    },
    clear(){
    this.todos=[]
    },
    remove(e){
e.target.parentElement.remove()
    }
  }
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

a,
button {
  color: #4fc08d;
  cursor:pointer;
}

button {
  background: none;
  border: solid 1px;
  border-radius: 2em;
  font: inherit;
  padding: 0.75em 2em;
  margin: 0px 20px;
}
  input{
    padding:0.75em 2em;
    text-align:center;
    border:1px solid;
    color:#4fc08d;
    font-size:1.1em;
    background:0;
  }
  button:focus{
    outline: none;
    transform:scale(1.1)
  }
  input:focus{
    outline: none;
  }
  li{
    list-style:none;
    margin: 10px 0;
  }
  body{
    background:#eee;
  }
  button:hover,input:focus{
    transform:scale(1.1)
  }
  @media only screen{
    button{
      margin: 10px;
    }
  }
</style>
