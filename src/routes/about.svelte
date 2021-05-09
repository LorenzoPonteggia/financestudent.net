<script>
    import {onMount} from "svelte"
    onMount(() => {
        document.title="About"
    });
</script>
<svelte:head>
  <title>About Page - FinanceStudent.net</title>
  <meta content="FinanceStudent.net About page, made by Lorenzo Ponteggia." name="Description">
</svelte:head>
<style>
    /* CSS for About page */
    @media only screen and (min-width:1000px){
        .aboutText{
            min-height: 63.5vh;
            color: #aaaaaa;
            font-size: 2.75vh;
            line-height: 1.2;
            min-height: 69.75vh
        }
        .aboutBox{
            margin: 1.5em 2.5em;
            padding: 1.5em;
            background-color: #303030;
        }
    }
    @media only screen and (max-width:999px){
        .aboutText{
            min-height: 63.5vh;
            color: #aaaaaa;
            font-size: 1.75vh;
            line-height: 1.2;
            min-height: 77vh
        }
        .aboutBox{
            margin: 2.5em;
            padding: 1.5em;
            background-color: #303030;
        }
    }
</style>
<div class="aboutText">
   <div class="aboutBox">
        <d>
            FinanceStudent.net is a website created by a fellow Finance student. <br>
            The aim of this website is to help students with their coursework and with the understanding of the subject.
            <br><br>
            The idea for this website sprung during the Covid-19 pandemic, as it had become harder to seek
            help fromprofessors and tutors, <br>
            the need for a simple and accessible tool that let's you check your coursework results became
            apparent.
        </d>
    <br><br>
        <d>
            FinanceStudent.net has been developed by <a
                href="https://www.linkedin.com/in/lorenzo-ponteggia-a7021a1a0/" style="color: #ff8200">Lorenzo
            Ponteggia</a>. <br>
            The website has been built using <a href="https://www.carbondesignsystem.com/" style="color: #bbbbbb">IBM Carbon Design System</a>,
            the calculators are powered by an api specifically developed using python. <br><br>
            The website and the api are hosted by Firebase.
            <br>
            Please find my LinkedIn Profile at the bottom of the page.
        </d>
    </div>    
</div>
