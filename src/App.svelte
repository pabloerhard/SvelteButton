<script>
import Button from './lib/Button.svelte'
import GoPrimitiveDot from 'svelte-icons/go/GoPrimitiveDot.svelte'
import DiGithubFull from 'svelte-icons/di/DiGithubFull.svelte'
</script>

<Button on:click={()=>alert(true)} let:isLeftHovered size={'large'} shadow={true} bgColor="red" textColor="white" >
    <div style:width="20px" slot="leftContent">
        {#if isLeftHovered}
        <DiGithubFull/>
        {:else}
        <GoPrimitiveDot />
        {/if}
    </div>
    Button 
</Button>

<style>

</style>