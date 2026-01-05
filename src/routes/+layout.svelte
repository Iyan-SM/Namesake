<script>
   import { onNavigate } from "$app/navigation";
   import { page } from '$app/stores';
   
	let { children } = $props();

   onNavigate((navigation) => {
      if (!document.startViewTransition) return;

      return new Promise((resolve) => {
         document.startViewTransition(async () => {
            resolve();
            await navigation.complete;
         });
      });
   });
</script>

<nav>
   <div class='bar short'> 
      <!-- {#if $page.url.pathname === '/'}
         <a href="/" class="deactivated">Home</a>
      {:else}
         <a href="/">Home</a>
      {/if} -->
   </div>

   <div class='bar med'>
      <!-- {#if $page.url.pathname === '/code'}
         <a href="/code" class="deactivated">Code</a>
      {:else}
         <a href="/code">Code</a>
      {/if} -->
   </div>

   <div class='bar long'> 
      <!-- {#if $page.url.pathname === '/portfolio'}
         <a href="/portfolio" class="deactivated">3D Art</a>
      {:else}
         <a href="/portfolio">3D Art</a>
      {/if}
   </div> -->
</nav>

<div>
    {@render children()}
</div>

<style>
 nav{
    position: absolute;
    left: 73%;
    font-family: "Fugaz One", sans-serif;
    font-weight: 400;
    font-style: normal;
    font-size: x-large;
    writing-mode: vertical-rl;
    display: flex;
    flex-direction: column-reverse;
    align-items: left;
    justify-content: right;
    row-gap: 2rem;
    margin-right: 1.2rem;
    margin-left: 1.2rem;
    margin-bottom: 1.2rem;
    view-transition-name: header;
 }
 .deactivated{
   pointer-events: none;
   user-select: none;
 }

 .bar{
    border-radius: 0px 0px 10px 10px;
    text-align: right;
    align-content: center;
    width: 3rem;
    position: relative;
    top: 0;
 }

 .short{
    background-color: #E6BCCD;
    box-shadow: 1px 1px 4px #c787a1;
    height: 10rem;
    transition: height ease 0.5s;
 }
 .short:not(.deactivated):hover{
    height: 10.4rem;
 }

 .med{
    background-color: #D295BF;
    box-shadow: 1px 1px 4px rgb(148, 86, 110);
    height: 17rem;
    transition: height ease 0.5s;
 }
 .med:not(.deactivated):hover{
    height: 17.4rem;
 }

 .long{
    background-color: #7E52A0;
    box-shadow: 1px 1px 4px #2e1542;
    height: 24rem;
    transition: height ease 0.5s;
 }
 .long:not(.deactivated):hover{
    height: 24.4rem;
 }

 hr{
   width: 35rem;
   margin-right: 0px;
   margin-top: 0px;
   border-top: 5px solid #C163A4;
 }
 a{
    text-decoration: none;
    color: white;
    margin-bottom: 1rem;

 }
 p{
    color: #C163A4;
    margin: 0;
    font-size:xx-large;
 }
 
/*Page Transitions*/

</style>