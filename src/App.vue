<template>
  <div id="app" class="container">
    <img src="./assets/logo.png" class="logo">
    <br>
    <h2>ToDo List</h2>
    <todo-list></todo-list>
    <br><hr><br>
    <h2>Send Form</h2>
    <send-form></send-form>
    <br><br><hr><br>
    <h2>Fetched data</h2>
    <fetch-data></fetch-data>
  </div>
</template>

<script>
import FetchData from './components/FetchData'
import TodoList from './components/TodoList'
import SendForm from './components/SendForm'

export default {
  name: 'App',
  components: {
    FetchData,
    TodoList,
    SendForm
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}

.container{
  max-width: 600px;
  margin:0 auto;
}


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
  font-size: 24px;
}

.logo{
  display:block;
  margin: 20px auto;
  height: 150px;
}
</style>
