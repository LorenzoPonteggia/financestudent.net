<script>
  import Calculator from "../lib/Calculator.svelte" 
  import Katex from "../utils/Katex.svelte"
  import {onMount} from "svelte"
  onMount(() => {
      document.title="Bond Value"
  });
  let inputsA = [
    {label: "Coupon", alias: "Coupon", icon: "dollar.svg"},
    {label: "Yield to Maturity", alias: "YieldToMaturity", icon: "percentage.svg"},
    {label: "Par or Face Value", alias: "parValue1", icon: "dollar.svg"},
    {label: "Number of Payments", alias: "numberOfPayments", icon: "number.svg"}
  ]
  let resIconA = "dollar.svg";

  let inputsB = [
    {label: "Coupon Rate", alias: "couponRate", icon: "percentage.svg"},
    {label: "Par or Face Value", alias: "parValue", icon: "dollar.svg"}
  ]
  let resIconB = "dollar.svg";

function formulaWriter(event){
  console.log(event.detail)
  formulaDinamic = ``
}

let formula = "Bond\\ Value=\\sum_{t=1}^{N}{\\frac{C}{(1+r_i)^t}+\\frac{{\\rm PV}_n}{(1+r_i)^N}}";
let formulaDinamic = "";
</script>


<svelte:head>
  <title>Bond Value | Pricing Calculator - FinanceStudent.net</title>
  <meta content="Bond Value Calculator, solve all your finance assignments in seconds! FinanceStudent.net is a website dedicated to students and professionals, completely free."
  name="Description">
</svelte:head>

<div class="CalcTitle">
  Bond Value Calculator
</div>
<div class="cgrid">

  <div class="ads hideOnMobile"></div>

  <div class="calcBox">
    <Calculator inputs = {inputsA} resIcon = {resIconA} endpoint = "BondPricing"/>
    <div class="centerText" style="font-size: 3vh; text-align: left;">Coupon Calculator</div>
    <Calculator inputs = {inputsB} resIcon = {resIconB} endpoint = "Coupon" on:result = {formulaWriter}/>
  </div>
  
  <div class="ads hideOnDesktop"></div>

    <div class="descriptionBox">
        <div class="calcDescription">
            <div>
                For bonds, the expected cash flows are coupons plus the par value.
            </div>

            <div class="formula">
                <Katex math={formula}/>
            </div>

            <div>
                <br>
                Where:
                <br> BP<sub>i</sub> = current price of the Bond
                <br> N = number of periods to maturity
                <br> C = Coupon Payment
                <br> PV<sub>N</sub> = Par Value of the Bond (also known as Face Value)
                <br> r<sub>i</sub> = Yield to Maturity (also knows as Discount Rate)<br>
            </div>
            <div>
                For More information about the Coupon, <a href="https://www.investopedia.com/terms/b/bond-valuation.asp">Click Here.</a>
            </div>
            <div>
                <br>If you are looking for a Coupon Calculator, <a href="/coupon">Click Here.</a>
            </div>
            <div>
                <br>If you are looking for a Yield To Maturity Calculator, <a href="/yield-to-maturity">Click Here.</a>
            </div>

        </div>
    </div>

  <div class="ads"></div>

</div>