<script>
	import Counter from "./Counter.svelte";
  	import Input from "./Input.svelte";
	const commonProps = {maxCounter: 15}

</script>

<!-- <Counter initialCounter={2}  {...commonProps}/>
<Counter initialCounter={10} {...commonProps}/>
<Counter {...commonProps}/> -->


<section>
	<h1>Search Movies 🍿</h1>
	<Input />
</section>


<style>
	h1 {
		font-size: 32px;
	}
	section {
		align-items: center;
		display: flex;
		flex-direction: column;
	}
</style>