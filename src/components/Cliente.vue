<template>
<div>
     <h2>{{ nome }}</h2>
     <h3>Descricao do cliente: {{ descricao }}</h3>
</div>
   
</template>

<script>
/* ✓ GOOD */
export default {
  name: 'ClienteDetail',
  // ...
  data() {
    return {
        id: 1,
        nome: 'Artur Todeschini Crestani',
        email: 'a@a.com',
        idade: 45,
        descricao: 'Programador/Analista'
    }
  }
}
</script>


<style scoped>

</style>
