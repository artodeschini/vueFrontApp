<template>
  <div id="form">
        <label>Nome:</label><br>
        <input type="text" v-model="nome">
        <input type="text" :data="nome">
        <br>
        <label>Descricao</label><br>
        <input type="text" v-model="descricao">
        <br>
        <label>Email</label><br>
        <input type="email" v-model="email">
        <br>
        <label>Idade</label><br>
        <input type="number" v-model="idade">
        <br>
        <button @click="addCliente($event)">Adicionar</button>
  </div>
</template>

<script>
export default {
name: 'DetailCliente',
  // ...
  data() {

  },
  props: {
    // id: Number,
    // nome: String,
    // email: String,
    // idade: Number,
    // descricao: String
    cliente: Object
  },
  methods: {
    addCliente: function($event) {
      console.log($event);
      this.cliente
    },

    emitirEvento: function() {
      console.log('emitido do filho');
      this.$emit("meDeleteCliente")
    }
  }
}
</script>

<style>

</style>