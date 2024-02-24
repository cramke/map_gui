<script>
    import Sidemenu from '../lib/Sidemenu.svelte';
	import Header from './Header.svelte';
	import './styles.css';
</script>

<div class="app">
	<Header />

	<main>
		<div id="SidemenuContainer">
			<Sidemenu />
		</div>
		<div id="BodyContainer">
			<slot />
		</div>
	</main>

	<footer>
		<p>visit <a href="https://github.com/cramke/risk_path">github/cramke/risk_path</a> to learn more</p>
	</footer>
</div>

<style>
	main {
		display: flex;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}

	#SidemenuContainer {
        flex: 1;
    }

    #BodyContainer {
        flex: 3;
    }

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
