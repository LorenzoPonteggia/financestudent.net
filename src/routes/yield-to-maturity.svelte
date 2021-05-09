<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Yield to Maturity Calculator"
  });
  let inputs = [
    {label: "Annual Coupon", alias: "AnnualCoupon", icon: "dollar.svg"},
    {label: "Par or Face Value", alias: "parValue", icon: "dollar.svg"},
    {label: "Market Price of Bond or Stock", alias: "MarketPrice", icon: "dollar.svg"},
    {label: "Number of years to Maturity", alias: "nOfYearsToMaturity", icon: "number.svg"},
  ]
  let resIcon = "percentage.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = ``
}

let formula = "";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Yield to Maturity Calculator - FinanceStudent.net</title>
  <meta content="Yield to Maturity Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Yield to Maturity Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "YieldToMaturity" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

  <div class="descriptionBox">
    <div class="calcDescription">
      <div>
            The <b>Yield to maturity</b> (YTM) is the total return anticipated on a bond if the bond is held until it
            matures. Yield to maturity is considered a long-term bond yield but is expressed as an annual rate.
            <br>
      </div>

      <div>
        For More information about the Coupon Rate, <a href="https://www.investopedia.com/terms/y/yieldtomaturity.asp">Click Here.</a>
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