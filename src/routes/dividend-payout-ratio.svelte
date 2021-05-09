<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Dividend Payout Ratio"
  });
  let inputs = [
    {label: "Dividends per Share", alias: "DividendsPerShare", icon: "dollar.svg"},
    {label: "Earnings per Share (EPS)", alias: "EarningsPerShare", icon: "dollar.svg"},
  ]
  let resIcon = "dollar.svg";

  let inputsB = [
    {label: "Company Net Income", alias: "CompanyNetIncome", icon: "dollar.svg"},
    {label: "Preferred Dividends", alias: "PreferredDividends", icon: "dollar.svg"},
    {label: "Number of Outstanding Shares", alias: "ShareN", icon: "number.svg"},
  ]
  let resIconB = "dollar.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `Dividend\\ Payout\\ Ratio=\\frac{${event.detail.formVals[0]}}{${event.detail.formVals[1]}}=\\$${event.detail.result}`
}
function formulaWriterB(event){
  console.log(event.detail)
  formulaDinamicB = `EPS=\\frac{${event.detail.formVals[0]}-${event.detail.formVals[1]}}{${event.detail.formVals[2]}}=\\$${event.detail.result}`
}

let formula = "Dividend\\ Payout\\ Ratio=\\frac{Dividend\\ per\\ Share}{Earnings\\ per\\ Share}";
let formulaDinamic = "";
let formulaB = "EPS=\\frac{Net\\ Profit\\ After\\ Taxes-Preferred\\ Dividends}{Number\\ of\\ Shares\\ Outstanding}";
let formulaDinamicB = "";
</script>


<svelte:head>
  <title>Dividend Payout Ratio Caluclator - FinanceStudent.net</title>
  <meta content="Dividend Payout Ratio Caluclator Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Dividend Payout Ratio Caluclator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "DividendPayoutRatio" on:result = {formulaWriter}/>
    <div class="centerText" style="font-size: 3vh; text-align: left;">Earnings per Share Caluclator</div>
    <Calculator inputs = {inputsB} resIcon = {resIconB} endpoint = "EarningsPerShare" on:result = {formulaWriterB}/>
  </div>
  <div class="ads hideOnDesktop"></div>

    <div class="descriptionBox">
        <div class="calcDescription">
            <div>
                The <b>Dividend Payout Ratio</b> is the ratio of the total amount of dividends paid out to shareholders relative to the net income of the company. It is the percentage of earnings paid toshareholders in dividends.
            </div>
            <div>
                For More information about Dividend Payout Ratio, <a href="https://www.investopedia.com/terms/d/dividendpayoutratio.asp">Click Here.</a>
            </div>
            <div class="formula">
                <Katex math={formula}/>
            </div>
            <div class="formula">
                <Katex math={formulaDinamic}/>
            </div>
            <div>
              <b>Earnings Per Share</b> (EPS) is the amount of annual earnings available to common stockholders, stated on a per-share basis. <br>
            </div>
            <div>
                For More information about EPS, <a href="https://www.investopedia.com/terms/e/eps.asp">Click Here.</a>
            </div>
            <div class="formula">
                <Katex math={formulaB}/>
            </div>
            <div class="formula">
                <Katex math={formulaDinamicB}/>
            </div>
        </div>
    </div>

  <div class="ads"></div>

</div>