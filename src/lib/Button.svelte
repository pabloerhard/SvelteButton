<script>
    export let size = 'small'
    export let shadow = false
    export let bgColor = undefined
    export let textColor =undefined
    let isLeftHovered

</script>

<button 
on:click

style:background-color={bgColor}
style:color={textColor}
class:size-lg={size==='large'}
class:size-sm={size==='small'}
class:shadow
>
{#if  $$slots.leftContent}
<div class="left-content" 
    on:mouseenter={()=>(isLeftHovered=true)}
    on:mouseleave={()=>(isLeftHovered=false)}>
    <slot  name="leftContent" />
</div>
{/if}
<slot {isLeftHovered}>FallBack</slot></button>

<style lang='scss'>
    button{
        display: flex;
        align-items: center;
        border:none;
        background: #ff3e00;
        color: white;
        
        font-weight: bold;
        border-radius: 10px;
        cursor: pointer;
        &:hover{
            background-image: linear-gradient(rgba(0,0,0,0.4)0 0);

        }
        &:active{
            background-image: linear-gradient(rgba(255,255,255,0.1)0 0);

        }
        &.disabled{
            opacity:0.8;
            cursor:not-allowed;
        }
        &.size-sm{
            padding: 15px 20px;
        }
        &.size-lg{
            padding: 20px 20px;
            font-size:20px;
        }
        &.shadow{
            box-shadow: 0 0 10px rgba(1,1,1,0.3);
        }
    
    }
    .left-content{
            margin-right: 10px;
        }
</style>