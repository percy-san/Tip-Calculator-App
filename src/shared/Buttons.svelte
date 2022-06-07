<script type="text/javascript">
	export let tip

	
</script>

<!--HTML-->
<div class="btn">
	<input type="button" value="{tip}%" on:click>
</div>

<!--CSS-->
<style type="text/css">
	input{
		text-align: center;
		padding:5px;
		width: 100%;
		height: 40px;
		color: white;
		border-radius:5px;
		font-size: 20px;
		background-color:hsl(183, 100%, 15%);
		border:none;
		cursor: pointer;
		transition: 0.2s ease-in-out;

	}
	input:hover{
		background-color:hsl(184, 14%, 56%);
		color: hsl(183, 100%, 15%);
	}

	input:focus{
		background-color:hsl(184, 14%, 56%);
		color: hsl(183, 100%, 15%);

	}
</style>


