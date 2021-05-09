<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Earnings per Share"
  });
  let inputs = [
    {label: "Company Net Income", alias: "CompanyNetIncome", icon: "dollar.svg"},
    {label: "Preferred Dividends", alias: "PreferredDividends", icon: "dollar.svg"},
    {label: "Number of Outstanding Shares", alias: "ShareN", icon: "number.svg"},
  ]
  let resIcon = "dollar.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `EPS=\\frac{${event.detail.formVals[0]}-${event.detail.formVals[1]}}{${event.detail.formVals[2]}}=\\$${event.detail.result}`
}

let formula = "EPS=\\frac{Net\\ Profit\\ After\\ Taxes-Preferred\ Dividends}{Number\\ of\ Shares\\ Outstanding}";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Earnings per Share EPS - FinanceStudent.net</title>
  <meta content="Earnings per Share (EPS) Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Earnings per Share (EPS) Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "EarningsPerShare" on:result = {formulaWriter}/>
  </div>
  <div class="ads hideOnDesktop"></div>

    <div class="descriptionBox">
        <div class="calcDescription">
            <div>
                <b>Earnings Per Share</b> (EPS) is the amount of annual earnings
                available to common stockholders, stated on a per-share
                basis. <br>
            </div>
            <div>
                For More information about EPS, <a href="https://www.investopedia.com/terms/e/eps.asp">Click Here.</a>
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