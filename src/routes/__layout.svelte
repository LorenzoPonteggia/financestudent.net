<script>
	import '../app.css';
  	import Navbar from "../lib/Navbar.svelte";
	import Footer from "../lib/Footer.svelte";
</script>

<svelte:head>
	<!-- Global site tag (gtag.js) - Google Analytics -->
	<script async src="https://www.googletagmanager.com/gtag/js?id=UA-173178499-1"></script>
	<script>
		window.dataLayer = window.dataLayer || [];
		function gtag(){dataLayer.push(arguments);}
		gtag('js', new Date());

		gtag('config', 'UA-173178499-1');
	</script>
	<script data-ad-client="ca-pub-3352760081213595" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
</svelte:head>

<Navbar/>

<slot />

<Footer/>

