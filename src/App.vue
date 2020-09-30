<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1 style="text-align: center">Basic register form</h1>
        <form>
            <label for="name">Name:</label><br>
            <input type="text" id="name" name="name"><br>
            <label for="surname">Surname:</label><br>
            <input type="text" id="surname" name="surname"><br>
            <label for="email">Email:</label><br>
            <input type="text" id="email" name="email"><br>
            <label for="legalPerson">Legal person:</label><br>
            <input type="text" id="legalPerson" name="legalPerson"><br>
            <label for="document">CPF/CNPJ:</label><br> <!-- only show CNPJ if Legal person = true. \n
            Use watch to show the desired field-->
            <input type="text" id="document" name="document"><br>
        </form>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <RegisterTable msg="This will be the register table"/>    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import RegisterTable from './components/RegisterTable.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    RegisterTable
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
