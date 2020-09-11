<div id="container">
    <div class="sub-container" on:click={() => {trocarTela(TELAS.HOME)}} >
        <div class="botoes">
            <div class="icones">
                <Icon icon={faHome}/>
            </div>
            <span>Home</span>
        </div>
    </div>
    <div class="sub-container" on:click={() => trocarTela(TELAS.AMIGOS)}>
        <div class="botoes">
            <div class="icones">
            <Icon icon={faUsers}/>
        </div>
        Amigos
        </div>
    </div>
    <div class="sub-container" on:click={() => trocarTela(TELAS.LIVROS)}>
        <div class="botoes">
            <div class="icones">
            <Icon icon={faBook}/>
        </div>
        Livros
        </div>
    </div>
    <div class="sub-container" on:click={() => trocarTela(TELAS.OPCOES)}>
        <div class="botoes">
            <div class="icones">
            <Icon icon={faUserCog}/>
        </div>
        Opções
        </div>
    </div>
</div>

<script context="module">
	export const TELAS = {
		HOME: 1,
		AMIGOS: 2,
		LIVROS: 3,
		OPCOES: 4
	}
</script>

<script>
    import Icon from 'fa-svelte'
    import { faHome } from '@fortawesome/free-solid-svg-icons/faHome'
    import { faUsers } from '@fortawesome/free-solid-svg-icons/faUsers'
    import { faBook } from '@fortawesome/free-solid-svg-icons/faBook'
    import { faUserCog } from '@fortawesome/free-solid-svg-icons/faUserCog'
    import { createEventDispatcher } from 'svelte'

    const dispatch = createEventDispatcher()

    function trocarTela(tela) {
        dispatch('mudarTela', tela)
    }
</script>

<style>
    #container {
		background-color: darkslategray;
		width: 100%;
		height: 5em;
		position: fixed;
		left: 0;
		bottom: 0;
        display: flex;
        justify-content: space-around;
	}

    .sub-container {
        width: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        color: whitesmoke;
    }

    .botoes {
        margin-left: auto;
        margin-right: auto;
    }

    .sub-container:hover {
        background-color: black;
    }

    .icones {
        font-size: 30px;
        text-align: center;
    }
</style>