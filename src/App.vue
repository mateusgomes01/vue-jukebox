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
            <!--
            <label for="legalPerson">Legal person:</label><br>
            <input type="checkbox" id="legalPerson" v-model="legalPerson">
            <label for="legalPerson">{{ legalPerson }}</label> -->
            <label for="legalPerson">Legal person? </label>
            <input
				type="checkbox"
				v-model="toggle"
				true-value="Yes"
				false-value="No"
            >
            <label for="checkbox">{{ toggle }}</label><br>
            <label for="CPF">CPF:</label><br> <!-- only show CNPJ if Legal person = true. \n
            Use watch to show the desired field-->
            <input type="text" id="CPF" name="CPF"><br>
            <label for="CNPJ">CNPJ:</label><br> <!-- only show CNPJ if Legal person = true. \n
            Use watch to show the desired field-->
            <input type="text" id="CNPJ" name="CNPJ"><br>
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
  data() {
    return {
		form: {
			name: 'Mateus Melo'
		},
		legalPerson: '',
		CNPJ: 'nullo',
		toggle: false,
    }
  },
  components: {
    HelloWorld,
    RegisterTable
  },
  watch: {
    // whenever legalPerson changes, this function will run
    /*legalPerson(newLegalPerson) {
      if (legalPerson) {
        this.showCNPJ();
      } else {
        this.hideCNPJ();
      }
    }*/
  },
  methods: {
      showCNPJ() {
        this.CNPJ = '...';
        this.CNPJ = '12345678';
      },
      hideCNPJ() {
        this.CNPJ = '...';
        this.CNPJ = 'nullo';
      }
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
