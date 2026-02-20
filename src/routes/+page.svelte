<script>
	function openInNewTab(url) {
		window.open(url, '_blank').focus();
	}
	let width = $state(200);

	function downloadResume(){
		const link = document.createElement('a');
		link.style.display = 'none';
		link.href = '/TDResume.pdf';
		link.download = 'Resume_Iyan_Syeed-Miller';

		// It needs to be added to the DOM so it can be clicked
		document.body.appendChild(link);
		link.click();

		// waits before removing for Firefox.
		setTimeout(() => {
			URL.revokeObjectURL(link.href);
			link.parentNode.removeChild(link);
		}, 0);
	}
</script>
<svelte:window bind:innerWidth={width}/>
<div class='page'>
	<br>
	<br>
	<header>
		<h1>Iyan <br>Syeed-Miller</h1>
	</header>
	<br>
	<div class="links">
		<button onclick={openInNewTab("mailto:iyansyeedmiller@gmail.com")} class="bioLink"><i class="fas fa-envelope"></i> <span>Iyansyeedmiller@gmail.com</span></button>
		<button onclick={openInNewTab("https://www.linkedin.com/in/iyan-syeed-miller/")} class="bioLink"><i class="fa-brands fa-linkedin"></i><span>LinkedIn</span></button>
		<button onclick={openInNewTab("https://github.com/Iyan-SM")} class="bioLink"><i class="fab fa-github"></i><span>GitHub</span></button>
		<button onclick={openInNewTab("https://www.youtube.com/@fireg5355")} class="bioLink"><i class="fab fa-youtube"></i> <span>Youtube</span></button>
	</div>
	<div class="bodyContainer">
		<div class="resumeBorder gradient">
			<span class='label'><p>Resume</p><button class='download' onclick={downloadResume()}><i class="fas fa-download"></i></button></span>
			<img  class="resume" src="TDResume.png" alt='Resume' style='width:100%; height:100%; border-radius:6px;'>
		</div>
		<!--
		<div class="thumbnailContainer">
			<div class="thumbnail gradient"></div>
			<div class="thumbnail gradient"></div>
			<div class="thumbnail gradient"></div>
		</div>
		-->
	</div>
</div>

<style>
	.page{
		padding: 20px;
	}
	h1{
		font-family: "Climate Crisis", sans-serif;
		font-optical-sizing: auto;
		font-weight: 400;
		font-style: normal;
		font-variation-settings:
			"YEAR" 1979;
		color: #29274C;
		font-size: calc(min(6.5vw, 90px));
		line-height: 8rem;
		margin-left: 5%;
		margin-right: 10%;
		margin-top: 4rem;
	}
	.links{
		display: flex;
		column-gap: 2rem;
		row-gap: 2rem;
		flex-wrap: wrap;
		color: #29274C;
		margin-left: 5%;
	}

	.bioLink {
		align-items: center;
		background-image: linear-gradient(144deg,#E6BCCD, #D295BF 20%, #7E52A0);
		border: 0;
		border-radius: 8px;
		box-shadow: rgba(151, 65, 252, 0.2) 0 15px 30px -5px;
		box-sizing: border-box;
		color: #FFFFFF;
		display: flex;
		font-family: Phantomsans, sans-serif;
		font-size: 1.2rem;
		justify-content: center;
		column-gap: 0.5em;
		padding: 8px 12px; 
		text-decoration: none;
		user-select: none;
		touch-action: manipulation;
		white-space: nowrap;
		cursor: pointer;
		transition: box-shadow ease 0.5s;
		margin-left: 20px;
		margin-right: 20px;
	}

	.bioLink:active,
	.bioLink:not([disabled]):hover {
		box-shadow:  -.125rem -.125rem 0.5rem #E6BCCD, .125rem .125rem 0.5rem #c085ee;
	}

	.bodyContainer{
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.resumeBorder{
		display: flex;
		flex-direction: column;
		padding: 20px;
		margin-left: 5vw;
		margin-top: 5rem;
		margin-right: 5vw;
		border-radius: 20px;
	}

	.resume{
		width: 55vw;
		height: 70vw;
	}

	.gradient{
		background-image: linear-gradient( #E6BCCD, #D295BF, #7E52A0);
	}

	.label{
		padding-left: 2vw;
		padding-right: 2vw;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		color: white;
		font-family: "Fugaz One", sans-serif;
		font-weight: 400;
		font-style: normal;
		font-size: 1.5rem;
		line-height: 0.2vw;

	}
	.download {
		background-color:#E6BCCD;
		border: 0;
		color: white;
		cursor: pointer;
	}
	

	/*Page Transitions*/
	/* :root {
	--paperAngle: 20deg;
	}

	@keyframes fade-in {
		from {
			opacity: 0;
		}
	}

	@keyframes fade-out {
		to {
			opacity: 0;
		}
	}

	@keyframes slide-from-top {
		from {
			transform: translateY(-100vh);
		}
	}

	@keyframes slide-from-bottom {
		from {
			transform: translateY(100vh);
		}
	}

	@keyframes spin {
	from {
		transform: rotate(20deg);
	}
	}


	:root::view-transition-old(root) {
	z-index: 1; 
	animation: 3000ms;
	}

	:root::view-transition-new(root) {
	z-index: 2;
		animation:
		1000ms cubic-bezier(0.4, 0, 0.2, 1) spin,
		210ms cubic-bezier(0, 0, 0.2, 1) 90ms fade-in,
		1000ms cubic-bezier(0.4, 0, 0.2, 1) slide-from-bottom;
	} */

	@media screen and (max-width: 1160px) {
		header {
			margin-top: 14rem;
		}

		.links {
			justify-content: space-around;
			margin-left: 0;
		}

		h1 {
			font-size: 8vw;
			line-height: 10vw;
			text-align: center;
		}

		.bioLink {
			font-size: 1.2em;
		}
	}

</style>