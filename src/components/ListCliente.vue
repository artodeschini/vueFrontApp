<template>

<div id="cliente">
    <h3>Cliente {{ cliente.nome }}</h3>
    <p>Codigo {{ cliente.id }}</p> 
    <p>Descricao {{ cliente.descricao }}</p>
    <p>Email {{ cliente.email }}</p>
    <p>Idade {{ cliente.idade }}</p>
    <button @click="emitirEvento($event)">Deletar</button>
</div>
   
</template>

<script>
/* ✓ GOOD */
export default {
  name: 'ListClientes',
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
    emitirEvento: function($event) {
      console.log($event);
      this.$emit("emitirEvento", { id: this.cliente.id, component: this});
    }
  }
}
</script>


<style scoped>
    #cliente {
        background-color: gray;
        padding: 1%; /* afasta das bordas */ 
        margin-top: 2%; /* separa o topo de cada */
    }

</style>
