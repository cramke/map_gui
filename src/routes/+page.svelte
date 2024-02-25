<script>
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<!-- body.html -->
	<div class="content">
		<h2>Content Area</h2>
		<p>This is the content area where the page content will be displayed.</p>
	</div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}
	.content {
        padding: 20px;
    }
</style>
