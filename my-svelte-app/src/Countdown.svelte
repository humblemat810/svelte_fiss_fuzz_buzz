<script>
    import { afterUpdate } from "svelte";
    import { onMount } from "svelte";

    export let countdown = 16;

    let timer = null
	let countdown2 = 30;
	$: displayValue = `00:${(countdown + countdown2).toString().padStart(2,0)}`
	onMount(()=> {
		setInterval(()=> {countdown -=1;}, 1000)
	})
    afterUpdate(()=>{
        
        if (countdown === 0){
            if (timer){
                clearInterval(timer);
            }
        }
    }
    )
</script>

<p>
    count: {displayValue}
    {#if (countdown % 3) === 0}
        {#if countdown % 5 === 0}  
           <p>buzz</p>
        {:else}
           <p>fizz</p>
        {/if}
    {:else if countdown % 5 === 0}
        <p>buzz</p>
    {/if}
</p>