<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Coupon Rate Calculator"
  });
  let inputs = [
    {label: "Coupon", alias: "coupon", icon: "dollar.svg"},
    {label: "Par or Face Value", alias: "parValue", icon: "dollar.svg"}
  ]
  let resIcon = "percentage.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = `Coupon\\ Rate\\%=\\frac{${event.detail.formVals[0]}}{${event.detail.formVals[1]}}=\\%${event.detail.result}`
}

let formula = "Coupon\\ Rate\\%=\\frac{Coupon}{Par\\ or\\ face\\ Value}";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Coupon Rate Calculator - FinanceStudent.net</title>
  <meta content="Bond Coupon Rate Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Coupon Rate Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputs} resIcon = {resIcon} endpoint = "CouponRate" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

  <div class="descriptionBox">
    <div class="calcDescription">
      <div>
          The <b>Coupon Rate</b> is a bond’s annual interest
          payment as a percentage of the bond’s par value. <br> <br>
          The coupon is a periodic cash flow that is paid
          by the issuer to the holder of the bond at set
          periods (usually annually or every 6 months). <br> <br>
          It can be thought of as a fixed interest payment. <br> <br>
          The Par Value or Face Value is the amount of money that the borrower must repay at the bond's
          maturity. <br>
      </div>

      <div>
        For More information about the Coupon Rate, <a href="https://www.investopedia.com/terms/c/coupon.asp">Click Here.</a>
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