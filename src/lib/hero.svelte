<script>
	import '../app.postcss';
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition'
	import { animateScroll } from 'svelte-scrollto-element';

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });

	let visible = false;
	onMount(()=>{
    requestAnimationFrame(()=>{
        setTimeout(()=>{
            visible = true
        }, 0)
    })
})

function scrollIntoView({ target }) {
		const el = document.querySelector(target.getAttribute('href'));
		if (!el) return;
    el.scrollIntoView({
      behavior: 'smooth'
    });
  }


let info = ""
export let start = ""
</script>

	{#if visible}
	<div in:fade>
		<div class="h-screen w-screen mx-auto flex justify-center items-center p-12">
			<div id="splash" class="w-full h-full bg-surface-700 rounded-3xl flex">
				<div id="pic" class="w-2/5 bg-[url(https://i.gifer.com/2WV9.gif)] rounded-tl-3xl rounded-bl-3xl">
		
				</div>
				<div class="divider-vertical h-full border-surface-800">
					
				</div>
				<div id="splash" class="w-3/5">
					<div class="text-center flex flex-col items-center justify-around h-full p-11">
						<h1 class="h-64 text-7xl bg-gradient-to-br from-primary-500 to-secondary-600 bg-clip-text text-transparent box-decoration-clone"><span class="h1 text-7xl bg-gradient-to-br from-secondary-500 to-primary-600 bg-clip-text text-transparent box-decoration-clone">Schedulix.</span> Your All-In-One College Schedule Solution!</h1>
						<br>
						<div class="flex flex-col">
							<div class="flex gap-24">
								<a href="{info}" class="btn btn-xl variant-ghost-primary bg-primary-500 w-48">Learn More</a>
								<a href="{start}"  class="btn btn-xl variant-filled-primary bg-primary-500 w-48">Start</a>
							</div>
							<div class="mt-8 text-tertiary-800 text-xl">Free, no sign ups, no credit cards</div>
						</div>
					</div>
				</div>
			</div>
		</div>
		
	</div>
	{/if}


