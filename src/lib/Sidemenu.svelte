<script>
	import github from '$lib/images/github.svg';
</script>

<!-- sidemenu.html -->
<nav>
    <ul class="sidemenu">
        <li><a href="/">Home</a></li>
        <li><a href="/map">Map</a></li>
        <li><a href="/map/tutorial">Map Tutorial</a></li>
        <li><a href="/settings">Settings</a></li>
    </ul>
    <div class="corner">
        <a href="https://github.com/sveltejs/kit">
            <img src={github} alt="GitHub" />
        </a>
    </div>
</nav>

<style>
    .sidemenu {
        background-color: #e5f5df;
        padding: 20px;
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

	.corner img {
		width: 2em;
		height: 2em;
		object-fit: contain;
	}
</style>
