<script>
    import {onMount} from "svelte"
    onMount(() => {
        document.title="Stocks"
    });
</script>

<svelte:head>
  <title>Stocks Calculators - FinanceStudent.net</title>
  <meta content="Finance Student - Stocks Calculators and Tools" name="Description">
</svelte:head>

<div class="grid">
    <div class="ads"></div>

    <div>
        <div class="centerText">Stocks Calcualtors</div>
        <div class="box">  
            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/earnings-per-share'">Earnings per Share</button>
            </div>
            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/pe-ratio'">P/E Ratio</button>
            </div>

            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/dividend-yield'">Dividend Yield</button>
            </div>
            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/dividend-payout-ratio'">Dividend Payout Ratio</button>
            </div>

            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/sharpe-ratio'">Sharpe Ratio</button>
            </div>
            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/holding-period-return'">HPR Holding Period Return</button>
            </div>
        </div>


    </div>
</div>