<template>
    <div class="teclado">
        <button 
        class="teclado-botao" 
        v-for="(letra, key) in 'abcdefghijklmnopqrstuvwxyz'" :key="key"
        :disable="verificarLetra(letra)"
        v-on:click="jogar(letra)">
        {{ letra }}
        </button>
    </div>
</template>
<script>
export default{
    name:'appTeclado',
    props:{
        letras:Array,
        verificarLetra: Function,
        jogar: Function
    },data() {
        return {}
    },methods:{},  
    components:{},
}
</script>
<style>
.teclado{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    width: 85%;
}
.teclado-botao{
    margin: 5px;
    margin-top: 20px;
    text-transform: uppercase;
}
</style>