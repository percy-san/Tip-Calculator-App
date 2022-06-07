<!--JS-->
<script type="text/javascript">

	export  let totalPerson = "0"
	export let tipsPerPerson = "0"
	

	
	
</script>
<!--HTML-->
<div class="results">
	<div class="total-amount-area">
		<div class="amounts">
			<div class="tip-amount">
				<p>Tips<span>/person</span></p>
				<h1 class="amount">${tipsPerPerson}</h1>
			</div>
			<div class="total-amount">
				<p>Total<span>/person</span></p>
				<h1 class="amount">${totalPerson}</h1>
			</div>
		</div>	
	</div>
	<button on:click>RESET</button>

</div>

<!--CSS-->
<style type="text/css">
	.results{
		background-color: hsl(183, 100%, 15%);
		border-radius: 15px;
		padding:25px;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.tip-amount, .total-amount{
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.tip-amount p, .total-amount p{
		color: white;
		font-size: 25px;
	}
	.tip-amount p span, .total-amount p span{
		color: grey;
		font-size: 15px;
	}

	.amount{
		color:hsl(172, 67%, 45%);
	}

	button{
		display: block;
		margin: 0 auto;
		width: 90%;
		border:none;
		background-color: hsl(172, 67%, 45%);
		color: white;
		border-radius: 5px;
		cursor: pointer;
		transition: 0.2s ease-in-out;
	}

	button:hover{
		background-color:hsl(184, 14%, 56%);
		color:hsl(183, 100%, 15%)
	}

	
</style>