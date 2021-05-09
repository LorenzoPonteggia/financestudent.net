<script>
    import { createEventDispatcher } from 'svelte';
    import {onMount} from "svelte"
    export let inputs = [];
    export let endpoint = "";
    export let resIcon = "";
    const dispatch = createEventDispatcher();

    let result = NaN;
    let formVals = [];

    // const baseURL = "https://financestudent.net/API/"
    const baseURL = "http://127.0.0.1:5000/API/"

    let url = "";

    onMount(() => {
        url = baseURL + endpoint;
    });

    function buildBody() {
        let body = {};
        inputs.forEach((input, i)=> {
            body[input.alias] = parseInt(formVals[i])
        });
        return JSON.stringify(body)
    }

    async function handleFetch() {
        try {
            let res = await fetch(url, {
                method: "POST",
                headers: {
                    'Accept': 'application/json',
                    'Content-Type': 'application/json'
                },
                body: buildBody(),
            });
            let data = await res.json();
            if (data.result) {
                result = data.result;
                dispatch("result", {
                    result: result, formVals: formVals
                })
            }
        } catch (e) {
            result = NaN;
        }
    }
    
</script>

<style>
    @media only screen and (min-width:1000px){
        .calcBox{
            display: flex;
            flex-wrap: wrap;
            flex-direction: row;
            justify-content: left;
            align-content: center;
            width: 85%;
            margin: 1.5vh 0;
            color: #aaaaaa;
            background-color: #404040;
        }
        .calcElement{
            margin: 2vh 0;
            margin-left: 2vh;
        }
        .calcResult{
            margin: 1vh 0vh;
            margin-left: 2vh;
        }
        .calcLabel {
            font-size: 2.5vh;
            color: #aaaaaa;
            text-align: center;
            margin-bottom: 8vh;
            font-size: 1.25vw;
        }
        .calcBut{
            width: auto;
            height: auto;
            padding: 0.25vw;
            font-size: 2vh;
            margin-left: 1.5vw;
        }
        .calcInput{  
            width: 10vw;
            font-size: 2.25vh;
            margin-left: 0.75vw;
            padding: 0.25vh;
            color: #ffffff;
            background-color: #606060;
            border: 0.02vh solid #ff8200;
            -moz-appearance: textfield;
            background-position: 0vh 0.5vh; 
            background-size: 1.25vw;
            background-repeat: no-repeat;
            padding-left: 1.35vw;
        }
        .calcInput:focus{
            border: 0.03vh solid red;
        }
        .calcInput::-webkit-outer-spin-button,
        .calcInput::-webkit-inner-spin-button {
            -webkit-appearance: none;
            margin: 0;
        }
        .calcInput[type=number] {
            -moz-appearance:textfield;
        }
    }

/* =============MOBILE =============================================================================================================*/

    @media only screen and (max-width:999px){
        .calcBox{
            display: flex;
            flex-wrap: wrap;
            flex-direction: row;
            justify-content: left;
            align-content: center;
            width: 100%;
            margin: 1.5vh 0;
            margin-left: 1.5vw;
            padding: 1vw;
            color: #aaaaaa;
            background-color: #404040;
        }
        .calcElement{
            width: 100%;
            margin: 2vh 0;
            margin-left: 2vh;
        }
        .calcResult{
            margin: 1vh 0vh;
            margin-left: 2vh;
        }
        .calcLabel {
            font-size: 2.5vh;
            color: #aaaaaa;
            text-align: center;
            margin-bottom: 8vh;
        }
        .calcBut{
            width: auto;
            height: auto;
            padding: 0.25vw;
            font-size: 2vh;
            align-content: center;
            margin-top: 1.5vh;
            margin-left: 1.5vw;
        }
        .calcInput{
            width: 60%;
            font-size: 2.25vh;
            margin-left: 0.75vw;
            padding: 0.25vh;
            color: #ffffff;
            background-color: #606060;
            border: 0.02vh solid #ff8200;
            -moz-appearance: textfield;
            background-position: 0vh 0.5vh; 
            background-size: 20px;
            background-repeat: no-repeat;
            padding-left: 6vw;
        }
        .calcInput:focus{
            border: 0.03vh solid red;
        }
        .calcInput::-webkit-outer-spin-button,
        .calcInput::-webkit-inner-spin-button {
            -webkit-appearance: none;
            margin: 0;
        }
        .calcInput[type=number] {
            -moz-appearance:textfield;
        }
    }
</style>

<div class="calcBox">
    {#each inputs as input, i}
        <div class="calcElement">
            <label class="calcLabel" for="">{input.label}</label>
            <input class="calcInput" min="0" onwheel="this.blur()" style="background-image: url({input.icon})" type="number" bind:value={formVals[i]} />
        </div>
    {/each}

    <div class="calcResult">
        <label class="calcLabel" for="">Result</label>
        <div class="hideOnDesktop"></div>
        <input class="calcInput" disabled style="background-image: url({resIcon})" bind:value={result} type="number"/>
        <button class="btn calcBut" on:click={() => handleFetch()}>Calculate</button>
    </div>
</div>