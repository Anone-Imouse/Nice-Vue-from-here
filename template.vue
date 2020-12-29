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
