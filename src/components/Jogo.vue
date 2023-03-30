<template>
        <div class="jogo">

           <appForca :erros="erros"/>

           <appPalavra :palavra="palavra" :dica="dica" :verificarLetra="verificarLetra" :etapa="etapa"/>

           <appTeclado
           v-if="etapa === 'jogo'"
           :letras="letras"
           :verificarLetra="verificarLetra"
           :jogar="jogar"
           />

           <appFinal
           v-if="etapa != 'jogo'"
           :etapa="etapa" :texto="etapa === 'ganhador'? 'Parabens :)' : 'Perdeu'"
           :jogarNovamente="jogarNovamente"/>
        </div>
</template>
<script>
import appForca from './Forca';
import appPalavra from './Palavra';
import appTeclado from './Teclado';
import appFinal from './Final';


export default{
    name:'appJogo',
    props:{
        erros: Number,
        palavra: String,
        dica: String,
        verificarLetra: Function,
        etapa: String,
        letras: Array,
        jogar: Function,
        jogarNovamente: Function
    }, 
    data() {
        return {}
    },
    methods:{
    },
    components:{
        appForca, appPalavra, appTeclado, appFinal
    }
}
</script>
<style>
.jogo{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
}
</style>