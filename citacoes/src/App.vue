<template>
	<div id="app">
		<!--ALTERNANDO ENTRE COMPONENTES-->
		<button @click="componente = 'Citacoes'">Citações</button>
		<button @click="componente = 'Sobre'">Sobre</button>

		<!--COMPONENTE DINAMICO -> tag component (tag especial do vue) -->
		<!-- :IS FAZ COM QUE O VUE INTERPRETE O COMPONENTE -->
		<!--PARA EVITAR QUE O COMPONENTE SEJA CRIADO E DESTRUÍDO SEMPRE QUE ENTRAR E SAIR, USAMOS KEE-ALIVE -->
		<!--<keep-alive>
		<component :is="componente"/>
		</keep-alive>-->

		
		<!--VC PODE USAR COM METODO DE CYCLO DE VIDA COM ACTIVATED E DEACTIVATED E NÃO USAR O KEEP-ALIVE, FAZENDO COM QUE O COMPONENTE SEJA CRIADO E DESTRUÍDO OU ATIVO OU DESATIVADO-->
		<component :is="componente"/>
	</div>
</template>

<script>
import Citacoes from './components/Citacoes'
import Sobre from './components/Sobre'

export default {
	components: { Citacoes, Sobre },
	data(){
		return{
			componente:'Citacoes'
		}
	}
}
</script>

<style>
	#app {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
		font-size: 1.6rem;
	}

	button {
        outline: none;
        padding: 5px 15px 10px;
        margin: 10px 5px;
        border-radius: 3px;
        font-size: 2rem;
        font-weight: 300;
        color: #FFF;
        background-color: rgba(0, 0, 0, .5);
    }
</style>