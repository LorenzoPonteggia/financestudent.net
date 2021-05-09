<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Margin Calculator"
  });
  let inputs = [
    {label: "Value of Securities", alias: "SecuritiesValue", icon: "dollar.svg"},
    {label: "Debit Balance", alias: "DebitBalance", icon: "dollar.svg"}
  ]
  let resIcon = "percentage.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `Margin\\ =\\ \\frac{${event.detail.formVals[0]}\\ -\\ ${event.detail.formVals[1]}}{${event.detail.formVals[0]}}=\\$${event.detail.result}`
}

let formula = "Margin\\ =\\ \\frac{Value\\ of\\ Securities\\ -\\ Debit\\ Balance}{Value\\ of\\ Securities}";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Margin Calculator - FinanceStudent.net</title>
  <meta content="Bond Margin Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Margin Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "MarginBase" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

  <div class="descriptionBox">
    <div class="calcDescription">
      <div>
        The <b>Margin</b> is the money borrowed from a brokerage firm to purchase an investment.
        <br><br>It is the difference between the total value of securities held in an investor's account and
        the loan amount from the broker. Buying on margin is the act of borrowing money to buy securities.
        <br><br>The practice includes buying an asset where the buyer pays only a percentage of the asset's
        value and borrows the rest from the bank or broker. The broker acts as a lender and the securities
        in the investor's account act as collateral. <br>
      </div>

      <div>
        For More information about the Margin, <a href="https://www.investopedia.com/terms/m/margin.asp">Click Here.</a>
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