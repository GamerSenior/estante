<script>
	import Menu, {TELAS} from './Menu.svelte'
	import Home from './views/Home.svelte'
	import Amigos from './views/Amigos.svelte'
	import Livros from './views/Livros.svelte'
	import Opcoes from './views/Opcoes.svelte'

	let telaAtual = TELAS.HOME;

	function mudarTela(evento) {
		alert("Tela atual: "  + evento.detail)
		telaAtual = evento.detail
	}
</script>

<main>
	{#if telaAtual === TELAS.HOME}
	<Home></Home>
	{:else if telaAtual === TELAS.AMIGOS}
	<Amigos></Amigos>
	{:else if telaAtual === TELAS.LIVROS}
	<Livros></Livros>
	{:else if telaAtual === TELAS.OPCOES}
	<Opcoes></Opcoes>
	{/if}

	<Menu on:mudarTela={mudarTela}></Menu>
</main>

<style>
	:global(body) {
		padding: 0;
	}

	main {
		background-color: aqua;
		height: 100%;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>