<template>
<div>
    <label>Nome:</label><br>
    <input type="text" v-model="nome"><!-- Databind two way-->
    <!-- <input type="text" :data="nome"> Databind one way-->
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
    <p>Cliente {{ nome }}</p> <!-- Databind one way-->
    <p>Descricao {{ descricao }}</p>
    <p>Email {{ email }}</p>
    <p>Idade {{ idade }}</p>
    
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
