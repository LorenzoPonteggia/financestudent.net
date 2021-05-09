<script>

</script>
<style>
    a { text-decoration: none; }
    @media only screen and (min-width:1000px){ 
        .navbarContainer{
            display: flex;
            flex-direction: row;
            background-color: #161616;
            justify-content: space-between;
            align-content: center;
        }
        .navbarContainer .navbarBoxR{
            display: flex;
            flex-direction: row;
            align-content: center;
            margin-left: 25px;
            margin-top: 1.5vh;
        }
        .navbarContainer .navbarBoxL{
            display: flex;
            flex-direction: row;
            align-content: center;
            margin-top: 1.5vh;
        }
        .navbarElement{
            margin-inline: 30px;
            font-size: 2.5vh;
            font-weight: 200;
            color: #aaaaaa;
        }
        .logo img{
            width: 3vw;
            margin-top: -1.5vh;
        }
        a:visited{
            color: #aaaaaa;
        }
        a:link{
            color: #aaaaaa;
        }
        a:hover{
            color: #aaaaaa;
        }
        a:active{
            color: #aaaaaa;
        }
    }
    /*==================================================================================================================*/

    /*Mobile*/
    @media only screen and (max-width:999px){   
        .navbarContainer{
            display: flex;
            flex-direction: row;
            background-color: #161616;
            justify-content: space-between;
            align-content: center;
        }
        .navbarContainer .navbarBoxR{
            display: flex;
            flex-direction: row;
            align-content: center;
            margin-left: 5px;
            margin-top: 1.5vh;
        }
        .navbarContainer .navbarBoxL{
            display: flex;
            flex-direction: row;
            align-content: center;
            margin-top: 1.5vh;
        }
        .navbarElement{
            margin-inline: 5px;
            font-size: 1.25vh;
            font-weight: 300;
            color: #aaaaaa;
        }
        .logo img{
            width: 3vh;
            margin-top: -0.75vh;
        }
        a:visited{
            color: #aaaaaa;
        }
        a:link{
            color: #aaaaaa;
        }
        a:hover{
            color: #aaaaaa;
        }
        a:active{
            color: #aaaaaa;
        }
    }
</style>
<div class="navbarContainer">

    <div class="navbarBoxR">

        <div class="navbarElement">
            <div class="logo"><img src="dollarLogo.png" alt="dollarLogo"></div>
        </div>

        <div class="navbarElement">
            <a href="/">Home</a>
        </div>

        <div class="navbarElement">
            <a href="/about">About</a>
        </div>

    </div>

    <div class="navbarBoxL">

        <div class="navbarElement">
            <a href="/bonds">Bonds</a>
        </div>

        <div class="navbarElement">
            <a href="/stocks">Stocks</a>
        </div>

        <div class="navbarElement">
            <a href="/margin-trading">Margin Trading</a>
        </div>

        <div class="navbarElement">
            <a href="/portfolio-analysis">Portfolio Analysis</a>
        </div>

    </div>
</div>