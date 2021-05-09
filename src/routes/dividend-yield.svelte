<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Dividend Yield Calculator"
  });
  let inputs = [
    {label: "Annual Dividends per Share", alias: "AnnualDividendsPerShare", icon: "dollar.svg"},
    {label: "Current Market Price of Share", alias: "CurrentMktPriceShare", icon: "dollar.svg"}
  ]
  let resIcon = "percentage.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `Dividend\\ Yield=\\frac{${event.detail.formVals[0]}}{${event.detail.formVals[1]}}=${event.detail.result}\\%`
}

let formula = "Dividend\\ Yield=\\frac{Annual\\ Divided\\ per\\ Share}{Price\\ per\\ Share}";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Coupon Calculator - FinanceStudent.net</title>
  <meta content="Dividend Yield Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Dividend Yield Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "DividendYield" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

  <div class="descriptionBox">
    <div class="calcDescription">
      <div>
        The <b>Dividend Yield</b>, expressed as a percentage, is a financial ratio that shows how much a company pays out in dividends each year relative to its stock price.
      </div>

      <div>
        For More information about the Dividend Yield, <a href="https://www.investopedia.com/terms/d/dividendyield.asp">Click Here.</a>
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