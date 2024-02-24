<script>
    import logo from '$lib/images/svelte-logo.svg';
	import github from '$lib/images/github.svg';
</script>

<!-- sidemenu.html -->
<nav class="sidemenu">
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/map">Map</a></li>
        <li><a href="/settings">Settings</a></li>
    </ul>

    <div class="corner">
		<a href="https://kit.svelte.dev">
			<img src={logo} alt="SvelteKit" />
		</a>
	</div>
    <div class="corner">
		<a href="https://github.com/sveltejs/kit">
			<img src={github} alt="GitHub" />
		</a>
	</div>
</nav>

<style>
    .sidemenu {
        height: 100%;
        background-color: #e5f5df;
        padding: 20px;
    }
    
    .sidemenu ul {
        list-style: none;
        padding: 0;
        margin: 0;
    }

    .sidemenu li {
        display: block;
        color: #000000;
        text-decoration: none;
        margin-bottom: 10px;
    }

    .sidemenu a {
        text-decoration: none;
        color: inherit;
    }

    .sidemenu a:hover {
        background-color: #98a591;
        padding: 10px;
        border-radius: 5px;
    }

    .corner {
		width: 3em;
		height: 3em;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner img {
		width: 2em;
		height: 2em;
		object-fit: contain;
	}
</style>
