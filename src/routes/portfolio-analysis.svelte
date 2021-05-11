<script>
    import {onMount} from "svelte"
    onMount(() => {
        document.title="Margin Trading"
    });
</script>

<svelte:head>
  <title>Margin Trading Calculators - FinanceStudent.net</title>
  <meta content="Finance Student - Margin Trading Calculators and Tools" name="Description">
</svelte:head>

<div class="grid">
    <div class="ads"></div>

    <div>
        <div class="centerText">Portfolio Analysis Calcualtors</div>
        <div class="box">  
            <div class="btn-wrap w-half">
                <button class="btn" onclick="window.location.href='/sharpe-ratio'">Sharpe Ratio</button>
            </div>
        </div>
    </div>
</div>
