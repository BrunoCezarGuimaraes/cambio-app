<template>
  <h1>Cálculo da Cotação</h1>
  <h2>Digite a quantidade em reais e a cotação do dólar:</h2>

  <div>
    <InputText id="input-reais" type="text" v-model="reais"/>
    <label for="input-reais" />
  </div>

  <div>
    <InputText id="input-cotacao" type="text" v-model="cotacao"/>
    <label for="input-cotacao" />
  </div>

  <div>
    <Button label="Limpar" @click="limpar"/>
    <Button label="Calcular" @click="calcular"/>
  </div>

  <div v-if="resultado">
    <p>Com R${{ reais }} é possivel comprar {{ resultado }} dólares na cotação de {{ cotacao }}</p>
  </div>
</template>

<script>


export default {
  data() {
    return {
      reais: null,
      cotacao: null,
      resultado: null
    }
  },
  methods: {
    calcular() {
      this.resultado = (this.reais / this.cotacao).toFixed(2);
    },
    limpar(){
      this.reais = null;
      this.cotacao = null;
      this.resultado = null;
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

Button {
  margin-left: 1rem !important;
}
</style>
