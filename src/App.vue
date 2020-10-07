<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1 style="text-align: center">Basic register form</h1>
        <form >
			<p>
				<label for="name">Name </label>
				<input v-model="form.name" placeholder="Your name">
			</p>
			<p>
				<label for="surname">Surname </label>
				<input v-model="form.surname" placeholder="Your surname"><br>
			</p>
			<p>
				<label for="email">Email </label>
				<input v-model="form.email" placeholder="Your email"><br>
			</p>
			<p>
				<label for="legalPerson">Legal person? </label>
				<input type="radio" id="yes" v-model="isLegal" v-bind:value="true">
				<label for="yes">Yes</label>
				<input type="radio" id="no" v-model="isLegal" v-bind:value="false">
				<label for="no">No</label><br>
			</p>
			<template v-if="isLegal">
				<p>
					<label for="cnpj">CNPJ </label>
					<input v-model="form.cnpj" placeholder="Your business CNPJ"><br>
				</p>
			</template>
			<template v-else>
				<p>
					<label for="cpf">CPF </label>
					<input v-model="form.cpf" placeholder="Your CPF"><br>
				</p>
			</template>

			<button @click.prevent="submit()">Save</button>
        </form>
    <RegisterTable msg="This will be the register table"/>
  </div>
</template>

<script>
import RegisterTable from './components/RegisterTable.vue'

export default {
  name: 'App',
  data() {
    return {
		form: {
			name: '',
			surname: '',
			email: '',
			isLegal: false,
			cnpj: '',
			cpf: '',
		},
		forms: [], // an array to store the forms
		isLegal: false
    }
  },
  components: {
    RegisterTable
  },
  watch: {
    // whenever toggle changes, this function will run
    isLegal: function(val) {
		console.log(val);
      if (val == true) {
        this.showCNPJ();
      } else {
        this.hideCNPJ();
      }
    }
  },
  methods: {
      showCNPJ() {
        this.form.isLegal = this.isLegal;
        this.form.cpf = '';
      },
      hideCNPJ() {
        this.form.isLegal = this.isLegal;
        this.form.cnpj = '';
      }
    },
	submit() {
		this.forms.push(this.form);
		this.form = {};
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

form  {
	margin: 0 auto; 
	width: 350px;
	display: table;
}

p     { 
	display: table-row; 
}

label {
	text-align: left;
	display: table-cell;
}
input {
	align-items: right;
	display: table-cell;
}

</style>
