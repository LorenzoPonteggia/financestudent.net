<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Sharpe Ratio"
  });
  let inputs = [
    {label: "Return", alias: "AverageReturnRate", icon: "percentage.svg"},
    {label: "Risk Free Rate", alias: "RiskFreeRate", icon: "percentage.svg"},
    {label: "Standard Deviation", alias: "StandardDeviation", icon: "number.svg"}
  ]
  let resIcon = "dollar.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `Sharpe\\ Ratio=\\ \\frac{${event.detail.formVals[0]}}{${event.detail.formVals[1]}}=\\$${event.detail.result}`
}

let formula = "Sharpe\\ Ratio=\\ \\frac{Return\\ -\\ Risk\\ Free\\ Rate}{Standard\\ Deviation}";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Sharpe Ratio Calculator - FinanceStudent.net</title>
  <meta content="Sharpe Ratio Calculator Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Sharpe Ratio Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "SharpeRatio" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

  <div class="descriptionBox">
    <div class="calcDescription">
      <div>
        The <b>Sharpe Ratio</b> is used to help investors understand the return of an investment compared to its risk.<br>
        The ratio is the average return earned in excess of the risk-free rate per unit of volatility ortotal risk.<br>
        Volatility is a measure of the price fluctuations of an asset or portfolio. <br>
      </div>

      <div>
        For More information about the Sharpe Ratio, <a href="https://www.investopedia.com/terms/s/sharperatio.asp">Click Here.</a>
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