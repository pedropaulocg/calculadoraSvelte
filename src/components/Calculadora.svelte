<script>
  import CalculadoraModel from '../model/CalculadoraModel'
  import Botao from "./Botao.svelte";
  import Linha from "./Linha.svelte";
  import Display from "./Display.svelte"
  
  let calc = new CalculadoraModel()
  const operacaoDigitada = (op) => calc = calc.opDigitada(op)
  const calcular = () => calc = calc.calcular()

</script>

<div class="calculadora">
  <Display valor={calc.valor}/>
  <Linha>
    <Botao triplo destaque btnTxt={"AC"} onClick ={() => calc = calc.limpar()}/>
    <Botao operacao btnTxt={"/"} />
  </Linha>

  <Linha>
    <Botao btnTxt={"7"} onClick={num => calc = calc.numeroDigitado(num)}/>
    <Botao btnTxt={"8"} onClick={num => calc = calc.numeroDigitado(num)}/>
    <Botao btnTxt={"9"} onClick={num => calc = calc.numeroDigitado(num)}/>
    <Botao operacao btnTxt={"*"} onClick={operacaoDigitada} />
  </Linha>

  <Linha>
    <Botao btnTxt={"4"} onClick={num => calc = calc.numeroDigitado(num)}/>
    <Botao btnTxt={"5"} onClick={num => calc = calc.numeroDigitado(num)} />
    <Botao btnTxt={"6"} onClick={num => calc = calc.numeroDigitado(num)}/>
    <Botao operacao btnTxt={"+"} onClick={operacaoDigitada}/>
  </Linha>
  <Linha>     
		<Botao btnTxt={'1'} onClick={num => calc = calc.numeroDigitado(num)}/>
		<Botao btnTxt={'2'} onClick={num => calc = calc.numeroDigitado(num)}/>
		<Botao btnTxt={'3'} onClick={num => calc = calc.numeroDigitado(num)}/>
		<Botao operacao btnTxt={'-'} onClick={operacaoDigitada}/>  
  </Linha>
  <Linha>     
		<Botao duplo btnTxt={'0'} onClick={num => calc = calc.numeroDigitado(num)}/>
		<Botao btnTxt={','} onClick = {()=> calc = calc.pontoDigitado()} />
		<Botao destaque btnTxt={'='} onClick={calcular}/>
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
