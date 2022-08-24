<script>
export default {
  data() {
    return {
      pessoa: "",
      conta: "",
      valor_gorjeta: "",
  }},
  methods: {
    calcular(){
      const pessoa = this.pessoa;
      const conta = this.conta;
      const valor_gorjeta = this.valor_gorjeta;
      let valor_valor_gorjeta = 0;
      let resultado = {};
      valor_valor_gorjeta = conta * (valor_gorjeta / 100);
      resultado = (conta + valor_valor_gorjeta) / pessoa;
      resultado = Math.round(resultado);
      document.getElementById("resultado").innerHTML = resultado;
    }
  },
};
</script>

<template>
  <div class="conteudo-oi">
    <h1>Calculadora de gorjetas</h1>
    <label> <p>Qual foi o valor da conta?</p>
      <input type="number" v-model="conta" id="conta">
    </label>

    <label>
      <p>Qual foi a qualidade do serviço?</p>
      <select v-model="valor_gorjeta">
        <option value="30">30% Excepcional</option>
        <option value="25">25% Muito bom</option>
        <option value="20">20% Bom</option>
        <option value="15">15% Ok</option>
        <option value="10">10% Ruim</option>
        <option value="5">5% Péssimo</option>
      </select>
    </label>

    <label><p>Quantas pessoas estão dividindo a conta?</p>
      <input type="number" v-model="pessoa" id="pessoa">
    </label>
    <button type="button" @click="calcular">R$:
      <span id="resultado"></span>
    </button>
  </div>
</template>
<style>
@import url('https://fonts.googleapis.com/css2?family=Russo+One&family=Silkscreen&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Yantramanav:wght@100;300&display=swap');
h1{
  color: #f95842;
  font-family: 'Russo One', sans-serif;
  font-size:50px;
}
p{
  font-family: 'Yantramanav', sans-serif;
}
button{
  background-color: #f95842;
  border:#ff4128;
  color: white;
  height:30px;
  width: 100px;
  border-radius:10px;
  margin:10px
}
</style>