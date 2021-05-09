<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Holding Period Return (HPR) Calculator"
  });
  let inputs = [
    {label: "Income", alias: "Income", icon: "dollar.svg"},
    {label: "End of Period Value", alias: "EndValue", icon: "dollar.svg"},
    {label: "Start of Period Value", alias: "StartValue", icon: "dollar.svg"},
  ]
  let resIcon = "percentage.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `HPR\\ =\\ \\frac{${event.detail.formVals[0]}\\ +\\ (${event.detail.formVals[1]}\\ -\\ ${event.detail.formVals[2]})}{${event.detail.formVals[2]}}=\\$${event.detail.result}`
}

let formula = "HPR\\ =\\ \\frac{Income\\ +\\ (End\\ of\\ Period\\ Value\\ -\\ Initial\\ Value)}{Initial\\ Value}";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Holding Period Return (HPR) Calculator - FinanceStudent.net</title>
  <meta content="Bond Holding Period Return (HPR) Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Holding Period Return (HPR) Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "HoldingPeriodReturn" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

  <div class="descriptionBox">
    <div class="calcDescription">
      <div>
        <d>The <b>Holding Period Return</b> (HPR) is the total return received from holding an asset or
            portfolio of assets over a period of time, known as the holding period, generally expressed as a
            percentage. <br>
      </div>

      <div>
        For More information about the Holding Period Return (HPR), <a href="https://www.investopedia.com/terms/h/holdingperiodreturn-yield.asp">Click Here.</a>
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