<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Coupon Calculator"
  });
  let inputs = [
    {label: "Coupon Rate", alias: "couponRate", icon: "percentage.svg"},
    {label: "Par or Face Value", alias: "parValue", icon: "dollar.svg"}
  ]
  let resIcon = "dollar.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `Coupon=\\frac{${event.detail.formVals[0]}\\ \}{100}\\times\ ${event.detail.formVals[1]}=\\$${event.detail.result}`
}

let formula = "Coupon=\\frac{Coupon\\ Rate\\ \\%}{100}\\times\ Par\\ or \\ Face\\ Value";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Coupon Calculator - FinanceStudent.net</title>
  <meta content="Bond Coupon Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Coupon Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "Coupon" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

  <div class="descriptionBox">
    <div class="calcDescription">
      <div>
        The <b>Coupon</b> is a periodic cash flow that is paid
        by the issuer to the holder of the bond at set
        periods (usually annually or every 6 months).
      </div>

      <div>
        For More information about the Coupon, <a href="https://www.investopedia.com/terms/c/coupon.asp">Click Here.</a>
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