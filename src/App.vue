<template>
  <div id="app">
      <h1>Hello World</h1>
  </div>
</template>

<script>
const soap = require('soap');

export default {
  created() {
    const url = 'https://arm.topsaude.com.br/WS/ServicosARM/wsdl/webServicePortal.wsdl';

    soap.createClient(url, function(err, client) {
      const args = {
        cia: 1,
        cpfNumeroCartao: '07292550932'
      };

      client.produtoBeneficiario(args, function(err, result) {
        console.log(result);
      });
    });
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
