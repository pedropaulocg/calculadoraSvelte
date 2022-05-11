<script>
    export let btnTxt = ''
    export let triplo = false
    export let duplo = false
    export let operacao = false
    export let destaque = false
    export let onClick = function onClick (valor) {
        
    }  
</script>


    <button class='botao'
    class:triplo
    class:duplo
    class:operacao
    class:destaque
    on:click={onClick(btnTxt)}
    >
        {btnTxt}
    </button>



<style>
    .botao {
        flex-basis: 25%;
        margin: 0;
        border: 1px solid var(--backColor);
    }
    .triplo {
        flex-basis: 75%;
    }
    .duplo {
        flex-basis: 50%;
    }
    .operacao {
        background-color: orange;
        color: #fff;
    }
    .destaque {
        background-color: red;
        color: white;
    }
</style>