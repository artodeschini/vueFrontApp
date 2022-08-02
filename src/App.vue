<template>
  <div id="app">
    <h3>Cadastro de Clientes:</h3>
    <small id="nomeErro" v-show="erro">Deu Erro verifique o nome</small>
    <label for="nome">Cliente</label>
    <input type="text" id="nome" name="nome" placeholder="Digite o nome do cliente" v-model="nomeField"/>
    <br>
    <label for="email">Email</label>
    <input type="text" id="email" name="email" placeholder="Digite o email do cliente" v-model="emailField"/>
    <br>
    <label for="idade">Idade</label>
    <input type="number" id="idade" name="idade" placeholder="Digite a idade do cliente" v-model="idadeField"/>
    <br>
    <label>Descricao</label>
    <select id="descricao" name="descricao" v-model="descricaoField">
      <option>Criança</option>
      <option>Analista TI</option>
      <option>Estudante</option>
    </select>
    <br>
    <button @click="cadastrarCliente">Cadastrar</button>
    <hr>
    <div v-for="(c, index) in clientes" :key="c.id">
      <p>{{ index  }}</p>
      <Cliente :cliente="c" @emitirEvento="deletarCliente"></Cliente>
    </div>
  </div>
</template>

<script>
// import Fomulario from './components/DetailCliente.vue';
import Cliente from './components/ListCliente.vue';

// import Produto from './components/Produto';

export default {
  name: 'App',
  
  data() {
    return {
      clientes: [
        {id: 1, nome: 'Artur', email: 'a@a.com', idade: 45, descricao: 'Analista TI'},
        {id: 2, nome: 'Catia', email: 'c@c.com', idade: 41, descricao: 'Analista TI'},
        {id: 3, nome: 'Manu', email: 'm@m.com', idade: 7, descricao: 'Criança'},
      ]
    }
  },
  components: {
    Cliente,
    // Produto
  },
  methods: {
    cadastrarCliente: function() {
      // como validar
      if (this.nomeField == undefined || this.nomeField.length < 3 ) {
        this.erro = true;
      } else {
        this.clientes.push(
          { id: Date.now(),
            nome: this.nomeField,
            email: this.emailField, 
            idade: this.idadeField, 
            descricao: this.descricaoField });

        this.nomeField = ''; 
        this.emailField = ''; 
        this.idadeField = ''; 
        this.nomeField = ''; 

        this.erro = false;
      }
    },
    deletarCliente: function($event) {
      console.log("recebendo o evento");
      //console.log($event);
      //console.log($event.id);
      let id = $event.id;
      let data = this.clientes.filter(cliente => cliente.id != id);
      // console.log(data);
      this.clientes = data;
    }
  }
}
</script>

<style>

#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */

}

#nomeErro {
  color: red;
}


</style>
