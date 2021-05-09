<script>
    import {onMount} from "svelte"
    onMount(() => {
        document.title="Bonds"
    });
</script>

<svelte:head>
  <title>Bonds Calculators - FinanceStudent.net</title>
  <meta content="Finance Student - Bonds Calculators and Tools" name="Description">
</svelte:head>

<div class="grid">
    <div class="ads"></div>

    <div>
        <div class="centerText">Bonds Calcualtors</div>
        <div class="box">  
            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/coupon'">Coupon</button>
            </div>
            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/coupon-rate'">Coupon Rate</button>
            </div>

            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/current-yield'">Current Yield</button>
            </div>
            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/yield-to-maturity'">Yield to Maturity</button>
            </div>

            <div class="btn-wrap w-full">
                <button class="btn" onclick="window.location.href='/bond-pricing'">Bond Pricing</button>
            </div>

            <div class="btn-wrap w-full">
                <button class="btn" onclick="window.location.href='/bond-value-first-payment'" style="font-size: 2vh;">Bond Value moments before its first coupon payment</button>
            </div>
        </div>
    </div>
    <div class="ads"></div>
</div>