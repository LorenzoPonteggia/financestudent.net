<svelte:head>
    <script type="text/javascript" src="https://platform.linkedin.com/badges/js/profile.js" async defer></script>
</svelte:head>

<style>
        /*footer for desktop */
    @media only screen and (min-width:1000px) {
        .stickToBottom{
            position: inherit;
            bottom: 0;
            width: 100vw;
        }
        .footer{
            display: flex;
		    flex-wrap: wrap;
            flex-direction: row;
		    justify-content: space-evenly;
            padding-top: 25px;
            padding-bottom: 25px;
            line-height: 1.25;
            background-color: #161616;
        }

        .footer .footer_section{
            background-color: inherit;
            color: #505050;
            font-size: .8vw;
            width: 18%;
            height: 100%;
            float: left;
        }
        .footer .footer_title{
            background-color: inherit;
            font-size: 1.5vw;
            font-weight:2vw;
            margin-left:-2px
        }
        .linkedIN{
            width: auto;    
        }
    }
    /*footer for mobile */
    @media only screen and (max-width:999px) {
        .stickToBottom{
            position: inherit;
            bottom: 0;
            width: 100vw;
        }
        .footer{
            display: flex;
		    flex-wrap: wrap;
            flex-direction: row;
		    justify-content: space-evenly;
            margin-top: 5vh;
            padding-top: 0.5vh;
            padding-bottom: 0.5vh;
            line-height: 1.25;
            background-color: #161616;
        }

        .footer .footer_section{
            background-color: inherit;
            color: #505050;
            font-size: 1vh;
            width: 18%;
            height: 100%;
            float: left;
        }
        .footer .footer_title{
            background-color: inherit;
            font-size: 2vh;
            font-weight: 300;
            margin-left:-2px
        }
        .linkedIN{
            display: none !important;
        }
    }
</style>
<div class="stickToBottom">
<div class="footer">
        <div class="footer_section">
            <div class="footer_title">Bonds</div>
            <a href="/coupon">Coupon</a> <br>
            <a href="/coupon-rate">Coupon Rate</a> <br>
            <a href="/current-yield">Current Yield</a> <br>
            <a href="/yield-to-maturity">Yield to Maturity</a> <br>
            <a href="/bond-pricing">Bond Pricing</a> <br>
            <a href="/bond-value-first-payment">Bond First Payment</a> <br>
        </div>

        <div class="footer_section">
            <div class="footer_title">Stocks</div>
            <a href="/earnings-per-share">Earnings per Share</a> <br>
            <a href="/pe-ratio">P/E Ratio</a> <br>
            <a href="/divident-yield">Dividend Yield</a> <br>
            <a href="/dividend-payout-ratio">Dividend Payout ratio</a> <br>
            <a href="/sharpe-ratio">Sharpe Ratio</a> <br>
            <a href="/holding-period-return">Holding Period Return</a> <br>
        </div>

        <div class="footer_section">
            <div class="footer_title">Margin Trading</div>
            <a href="/margin-base">Margin</a> <br>
            <a href="/margin-call-price">Margin Call Price</a> <br>
            <a href="/margin-call-price-short">Short Margin Call Price</a> <br>
        </div>

        <div class="footer_section">
            <div class="footer_title">Portfolio Analysis</div>
            <a href="/#">Sharpe Ratio</a> <br>
        </div>
        <div class="linkedIN">
            <a href='https://uk.linkedin.com/in/lorenzo-ponteggia-a7021a1a0?trk=profile-badge'>Lorenzo Ponteggia</a>
        </div>
    </div>
</div>
