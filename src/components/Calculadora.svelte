<script>
  import Botao from "./Botao.svelte";
  import Linha from "./Linha.svelte";
  import Display from "./Display.svelte"
  
  class Model {
    constructor(valor = '0') {
      this.valor = valor
    }
  }
  let obj = new Model()
  

  function numeroDigitado(numero) {
    obj.valor += numero
  }
  

</script>

<div class="calculadora">
  <Display valor={obj.valor}/>
  <Linha>
    <Botao triplo destaque btnTxt={"AC"} />
    <Botao operacao btnTxt={"/"} />
  </Linha>

  <Linha>
    <Botao btnTxt={"7"} onClick={numeroDigitado}/>
    <Botao btnTxt={"8"} onClick={numeroDigitado}/>
    <Botao btnTxt={"9"} onClick={numeroDigitado}/>
    <Botao operacao btnTxt={"*"} />
  </Linha>

  <Linha>
    <Botao btnTxt={"4"} onClick={numeroDigitado}/>
    <Botao btnTxt={"5"} onClick={numeroDigitado}/>
    <Botao btnTxt={"6"} onClick={numeroDigitado}/>
    <Botao operacao btnTxt={"+"} />
  </Linha>
  <Linha>     
		<Botao btnTxt={'1'} onClick={numeroDigitado}/>
		<Botao btnTxt={'2'} onClick={numeroDigitado}/>
		<Botao btnTxt={'3'} onClick={numeroDigitado}/>
		<Botao operacao btnTxt={'-'}/>  
  </Linha>
  <Linha>     
		<Botao duplo btnTxt={'0'} onClick={numeroDigitado}/>
		<Botao btnTxt={','} onClick={numeroDigitado}/>
		<Botao destaque btnTxt={'='}/>
  </Linha>
</div>

<style>
  .calculadora {
    background-color: var(--backColor);
    display: flex;
    height: 220px;
    width: 150px;
    padding: 10px;
    border-radius: 10px;
    flex-direction: column;
  }
</style>
