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
        <div class="centerText">Margin Trading Calcualtors</div>
        <div class="box">  
            <div class="btn-wrap w-full ">
                <button class="btn" onclick="window.location.href='/margin-base'">Margin</button>
            </div>

            <div class="btn-wrap w-full">
                <button class="btn" onclick="window.location.href='/margin-call-price'">Margin Call Price</button>
            </div>

            <div class="btn-wrap w-full">
                <button class="btn" onclick="window.location.href='/margin-call-price-short'">Margin call Price when Short Selling</button>
            </div>
        </div>
    </div>
</div>
