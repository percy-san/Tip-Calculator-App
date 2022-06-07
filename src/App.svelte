<!--JS-->
<script>
	import Buttons from './shared/Buttons.svelte'
	import Right from './Right.svelte'

	//OBJECT HOLDING ALL THE TIP VALUES
	let tipsValue = [
    {percentage:5,id:1},
    {percentage:10,id:2},
    {percentage:15,id:3},
    {percentage:25,id:5},
    {percentage:50,id:6},
   
  ]

  //OBJECT HOLDING ERROR MESSAGES FOT INPUT BOXES
  let errors ={amount:"",people:""}
	

  	
	let bill 
	let people 
	let tip = 0
	let customTip
	
	//CALCULATE CUSTOM TIPS
	$: totalTips = `${(customTip/100)}`*`${bill}`
	$: tipsPerPerson = Math.round(`${totalTips}`/`${people}`).toFixed(2) 

	//CALCULATE TOTAL EACH PERSON HAS TO PAY
	$: totalPerson = Math.round(`${bill}`/`${people}`)

	//CALCULATE TIPS FROM SELECED BUTTON
	$: totalTips = `${(tip/100)}`*`${bill}`
	$: tipsPerPerson = Math.round(`${totalTips}`/`${people}`).toFixed(2)


	//HANDLES THE RETREIVING OF THE BUTTON VALUES AND RETURNS 
	//IT TO BE USED OUTSIDE THE FUCTION
	const handletip = (value) =>{
		tip = value
		customTip = 0
		return tip
	}

	//RESETS ALL VALUES BACK TO THEIR ORIGINAL ONES
	const  reset = () =>{
		totalPerson =""
		bill =""
		people =""
		customTip = ""
		tip = 0
	}

	

	


</script>

<!--HTML-->
<img src="../images/logo.svg" alt="logo">

<main>
	<div class="left">
		<div class="bill-area">
			<p class="sect-title">Bill:</p>
			<i class="fa-solid fa-dollar-sign"><span><input type="number" bind:value={bill}></span></i>
			
		</div>
		<div class="tip-area">
			<p class="sect-title">Select Tip: {tip}% </p>
			<form>
				<div class="tip-btn-area">
					{#each tipsValue as value (value.percentage)}
						<Buttons tip={value.percentage}  on:click={() => handletip(value.percentage)}/>
					{/each}
					<input type="number"  class="cust-tip" placeholder="Custom" bind:value={customTip}>
				</div>
			</form>
		</div>

		<div class="people">
			<p class="sect-title">Number of people:</p>
			<i class="fa-solid fa-user"><span><input type="number" bind:value={people} required></span></i>	
			
		</div>
	</div>

	<Right {totalPerson} {tipsPerPerson} on:click={reset}/>
		
	
</main>

<!--CSS-->
<style type="text/css">
	img{
		display: block;
		margin: 0 auto;
		margin-top:40px;
		margin-bottom:20px;  

	}
	main{
		display: block;
		margin:0 auto;
		width: 80%;

		padding:30px;
		background-color: hsl(0,0%,100%);
		border-radius:15px;

		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: 1fr;
		grid-gap: 15px;
	}

	i{
		display: flex;
		align-items: center;
		justify-content: space-between;
		font-size:20px;
		
	}
	
	input{
		color: hsl(183, 100%, 15%);
		font-weight: bold;
		font-size: 18px;
		width: 100%;
		transition: 0.2s ease-in-out;
		
	}
	input:hover{
		border:1px solid hsl(172, 67%, 45%);
	}
	.cust-tip{
		font-size:15px;
		width: 100px !important;
	}
	.sect-title{
		margin-bottom: 10px;
		font-size:20px;
	}
	.tip-btn-area{
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		grid-template-rows: 1fr 1fr;
		grid-gap: 20px;
	}

/******BREAKPOINTS******/
@media screen and (max-width: 700px){
	main{
		display: grid;
		grid-template-columns: 1fr;
		grid-template-rows: 1fr 1fr;




	}
}

	
</style>
