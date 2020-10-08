<template>
  <div class="registerTable">
    <h2>{{ form.name }}</h2>
  </div>  
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    form: {}
  },
  data () {
    return {
      employee: 'Mateus Melo',
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
