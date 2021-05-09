<script>
    import {onMount} from "svelte"
    onMount(() => {
        document.title="FinanceStudent.net"
    });

</script>
<svelte:head>
  <title>FinanceStudent.net - Homepage</title>
  <meta content="FinanceStudent.net - Financial Calcualtors." name="Description">
</svelte:head>
<style>

</style>
<div style="min-height: 66vh;">
<div class="boxHome">
    <div class="btn-wrap w-halfHome">
        <button class="btn" onclick="window.location.href='/bonds'">Bonds</button>
        <div class="btn-label">All the calculators related to Bonds!</div>
    </div>

    <div class="btn-wrap w-halfHome">
        <button class="btn" onclick="window.location.href='/stocks'">Stocks</button>
        <div class="btn-label">All the calculators related to Stocks!</div>
    </div>

    <div class="btn-wrap w-halfHome">
        <button class="btn" onclick="window.location.href='/margin-trading'">Margin Trading</button>
        <div class="btn-label">All the calculators related to Margin Trading!</div>
    </div>
    <div class="btn-wrap w-halfHome">
        <button class="btn" onclick="window.location.href='/portfolio-analysis'">Portfolio Analysis</button>
        <div class="btn-label">All the calculators related to Portfolio Analysis!</div>
    </div>
</div>
</div>