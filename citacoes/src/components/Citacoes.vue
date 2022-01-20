<template>
    <div class="citacoes">
        <span>
            <button @click="numero--">&lt;</button>
            <button @click="numero++">&gt;</button>
        </span>
        <!--QUANDO COLOCA :CITACOES PEDE QUE O VUE INTERPRETE ESSE VALOR-->
        <!--citacoes[indice].texto PASSA INDICE TEXTO COMO BUSCA-->
        <citacao>
            <!--INTERPOLANDO O VALOR DE TEXTO DENTRO DO ELEMENTO P-->
            <!--SLOT POR NOME-->
            <h1 slot="autor">{{citacoes[indice].autor}}</h1>
            <p slot="texto">{{citacoes[indice].texto}}</p>
            <h6 slot="fonte">{{citacoes[indice].fonte}}</h6>
            <!--FAZ COM QUE O TEXTO SEJA EXIBIDO NO COMPONENTE CITACAO-->
        </citacao>
    </div>
</template>

<script>
import citacao from './Citacao.vue'

export default {
  components: { citacao },
    data() {
        return {
            numero: 0,
            citacoes: [{
                fonte: 'Jornal do Empreendedor',
                texto: 'Lembre-se sempre que você é absolutamente único. Assim como todos os outros.',
                autor: 'Margaret Mead'
            }, { 
                fonte: 'Frases de Mãe',
                texto: 'Isso não é um quarto, é um chiqueiro.',
                autor: 'Roberta'
            }, {
                fonte: 'Frases de Pai',
                texto: 'Vou contar até 3! 1, 2, 2...',
                autor: 'Gustavo'
            }]
        }
    },
    computed: {
        indice() {
            return Math.abs(this.numero % 3)
        }
    },
    created(){
        console.log('created')
    },
    destroyed(){
        console.log('destroyed')
    },
    activated(){
        console.log('activated')
    },
    deactivated(){
        console.log('deactivated')
    }
}
</script>

<style scoped>
    .citacoes {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>
