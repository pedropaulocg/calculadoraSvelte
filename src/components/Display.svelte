<script>
    export let valor

    $: tamanhoFont = valor.length > 20 ? 'pequena' : `s-${valor.length}`
</script>

<div class={`tela ${tamanhoFont}`}>
    <span>
        {valor}
    </span>
</div>

<style>
    .tela {
        display: flex;
        background-color: aliceblue;
        flex: 1;
        justify-content:  flex-end;
        align-items: center;
        padding:0 5px;
        overflow: hidden;
        font-size: 1.7rem;
    }
    .s-10 {font-size: 1.5rem;}
    .s-11 {font-size: 1.35rem;}
    .s-12 {font-size: 1.25rem;}
    .s-13 {font-size: 1.15rem;}
    .s-14 {font-size: 1.07rem;}
    .s-15 {font-size: 1rem;}
    .s-16 {font-size: .93rem;}
    .s-17 {font-size: .87rem;}
    .s-18 {font-size: .83rem;}
    .s-19 {font-size: .78rem;}
    .s-20 {font-size: .74rem;}

    .pequena {font-size: 0.6rem;}
</style>