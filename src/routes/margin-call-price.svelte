<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Margin Call Price Calculator"
  });
  let inputs = [
    {label: "Initial Margin", alias: "InitialMargin", icon: "percentage.svg"},
    {label: "Maintenance Margin", alias: "MaintenanceMargin", icon: "percentage.svg"},
    {label: "Stock Price", alias: "StockPrice", icon: "dollar.svg"}
  ]
  let resIcon = "dollar.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `Margin\\ Call\\ Price\\ =\\ ${event.detail.formVals[2]}\\times(\\frac{1-(\\frac{${event.detail.formVals[0]}}{100})}{1-(\\frac{${event.detail.formVals[1]}}{100})})=\\$${event.detail.result}`
}

let formula = "Margin\\ Call\\ Price\\ =\\ {Stock\\ Price}\\times(\\frac{1-(\\frac{Initial\\ Margin\\%}{100})}{1-(\\frac{Maintenance\\ Margin\\%}{100})})";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Margin Call Price Calculator - FinanceStudent.net</title>
  <meta content="Bond Margin Call Price Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Margin Call Price Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "MarginCallPrice" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

  <div class="descriptionBox">
    <div class="calcDescription">
      <div>
        A <b>Margin Call</b> occurs when the value of an investor's margin account falls below the broker's 
        required amount.
        <br><br>An investor's margin account contains securities bought with borrowed money (typically a
        combination of the investor's own money and money borrowed from the investor's broker).
        <br><br>A margin call refers specifically to a broker's demand that an investor deposit additional
        money or securities into the account so that it is brought up to the minimum value, known as the
        maintenance margin. <br>
      </div>

      <div>
        For More information about the Margin Call Price, <a href="https://www.investopedia.com/terms/c/callprice.asp">Click Here.</a>
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