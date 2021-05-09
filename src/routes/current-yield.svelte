<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Current Yield Calculator"
  });
  let inputs = [
    {label: "Annual Interest Income", alias: "AnnualInterestIncome", icon: "dollar.svg"},
    {label: "Current Market Price of Bond", alias: "CurrentMKTPriceOfBond", icon: "dollar.svg"}
  ]
  let resIcon = "percentage.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `Current \\ Yield\\ \\% =\\frac{${event.detail.formVals[0]}}{${event.detail.formVals[1]}}={${event.detail.result}}\\%`
}

let formula = "Current \\ Yield\\ \\% =\\frac{Annual\\ Coupon\\ Income}{Current\\ Market\\ Price\\ of\\ Bond}";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Current Yield Calculator - FinanceStudent.net</title>
  <meta content="Current Yield Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Current Yield Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "CurrentYield" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

  <div class="descriptionBox">
    <div class="calcDescription">
      <div>
            The <b>Current Yield</b> is the simplest form of bond return measure, it only takes into
            consideration the current income. <br>
            For More information about the Current Yield,
      </div>

      <div>
        For More information about the Current Yield, <a href="https://www.investopedia.com/ask/answers/051215/what-difference-between-bonds-yield-rate-and-its-coupon-rate.asp">Click Here.</a>
      </div>

      <div class="formula">
        <Katex math={formula}/>
      </div>

      <div class="formula">
        <Katex math={formulaDinamic}/>
      </div>
    </div>
  </div>

  <div class="ads"></div>

</div>