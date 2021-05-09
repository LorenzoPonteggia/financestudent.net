<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="PE Ratio"
  });
  let inputs = [
    {label: "Market Price of Stock", alias: "PriceCommonStock", icon: "dollar.svg"},
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
  formulaDinamic = `P/E=\\frac{${event.detail.formVals[0]}}{${event.detail.formVals[1]}}=\\$${event.detail.result}`
}
function formulaWriterB(event){
  console.log(event.detail)
  formulaDinamicB = `EPS=\\frac{${event.detail.formVals[0]}-${event.detail.formVals[1]}}{${event.detail.formVals[2]}}=\\$${event.detail.result}`
}

let formula = "P/E=\\frac{Price\\ of\\ Common\\ Stock}{Earnings\\ per\\ Share}";
let formulaDinamic = "";
let formulaB = "EPS=\\frac{Net\\ Profit\\ After\\ Taxes-Preferred\\ Dividends}{Number\\ of\\ Shares\\ Outstanding}";
let formulaDinamicB = "";
</script>


<svelte:head>
  <title>PE Ratio (P/E Ratio) Caluclator - FinanceStudent.net</title>
  <meta content="PE Ratio (P/E Ratio) Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  PE Ratio (P/E) Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "PERatio" on:result = {formulaWriter}/>
    <div class="centerText" style="font-size: 3vh; text-align: left;">Earnings per Share Caluclator</div>
    <Calculator inputs = {inputsB} resIcon = {resIconB} endpoint = "EarningsPerShare" on:result = {formulaWriterB}/>
  </div>
  <div class="ads hideOnDesktop"></div>

    <div class="descriptionBox">
        <div class="calcDescription">
            <div>
                The <b>Price-to-Earnings Ratio</b> (P/E) is used to determine how the market is pricing the company’s common stock. <br>
            </div>
            <div>
                For More information about EPS, <a href="https://www.investopedia.com/terms/p/price-earningsratio.asp">Click Here.</a>
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