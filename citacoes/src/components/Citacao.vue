<template>
    <div class="citacao">
        <!--INTERPOLAR-->
        <!--AGORA ESSE COMPONENTE ESPERA RECEBER UMA PROPRIEDADE CHAMADA TEXTO
        {{texto}}-->
        <!--SLOT SERVE PARA EXIBIR O QUE FOI PASSADO DENTRO DO CORPO DO COMPONENTE-->
        <!--PASSANDO CONTEÚDO SLOT POR NOME-->
        <slot name="fonte"></slot>
        <slot name="texto"></slot>
        <slot name="autor"></slot>
    </div>
</template>

<script>
export default {
    /*props:{
        //ESPERANDO RECEBER UM TEXTO
        props:['texto']
    },*/
    //O COMPONENTE SEMPRE É DESTRUÍDO E CRIADO NO FLUXO, TEMOS UMA OPÇÃO QUANDO NÃO QUEREMOS QUE SEJA DESTRUÍDO
    /*created(){
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
    }*/
}
</script>

<style scoped>
    .citacao {
        border: 1px solid #DDD;
        background-color: rgba(0, 0, 0, .1);
        padding: 25px;
        max-width: 450px;
    }
</style>
