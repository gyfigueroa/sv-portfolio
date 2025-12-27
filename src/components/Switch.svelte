<script>
    // based on suggestions from:
    // Inclusive Components by Heydon Pickering https://inclusive-components.design/toggle-button/
    // On Designing and Building Toggle Switches by Sara Soueidan https://www.sarasoueidan.com/blog/toggle-switch-design/
    // and this example by Scott O'hara https://codepen.io/scottohara/pen/zLZwNv 

    export let label;
    export let design = 'inner label'
    export let options = [];
		export let fontSize = 16;
	  export let value = 'on';

    let checked = true;


		const uniqueID = Math.floor(Math.random() * 100)

    function handleClick(event){
        const target = event.target

        const state = target.getAttribute('aria-checked')

        checked = state === 'true' ? false : true

        value = checked === true ? 'on' : 'off'
    }
	
	  const slugify = (str = "") =>
    str.toLowerCase().replace(/ /g, "-").replace(/\./g, "");

</script>

{#if design == 'inner'}
<div class="s s--inner">
    <span id={`switch-${uniqueID}`}>{label}</span>
    <button
        role="switch"
        aria-checked={checked}
        aria-labelledby={`switch-${uniqueID}`}
        on:click={handleClick}>
            <span>on</span>
            <span>off</span>
    </button>
</div>
{:else if design == 'slider'}
<div class="s s--slider" style="font-size:{fontSize}px">
    <span id={`switch-${uniqueID}`}>{label}</span>
    <button
        role="switch"
        aria-checked={checked}
        aria-labelledby={`switch-${uniqueID}`}
        on:click={handleClick}>
    </button>
</div>
{:else}
<div class="s s--multi">
    <div role='radiogroup'
				 class="group-container"
				 aria-labelledby={`label-${uniqueID}`}
				 style="font-size:{fontSize}px" 
				 id={`group-${uniqueID}`}>
    <div class='legend' id={`label-${uniqueID}`}>{label}</div>
        {#each options as option}
            <input type="radio" id={`${option}-${uniqueID}`} value={option} bind:group={value}>
            <label for={`${option}-${uniqueID}`} class="label">
                {option}
            </label> 
        {/each}
    </div>
</div>

{/if}

<style>
			:root {
		--accent-color: CornflowerBlue;
		--gray: #ccc;
        --scaleunit: 2;
	}
    /* Inner Design Option */
    .s--inner button {
        padding: 0.5em;
        background-color: #fff;
        border: 1px solid var(--gray);
    }
    [role='switch'][aria-checked='true'] :first-child,
    [role='switch'][aria-checked='false'] :last-child {
        display: none;
        color: #fff;
    }

    .s--inner button span {
        user-select: none;
        pointer-events:none;
        padding: 0.25em;
    }

    .s--inner button:focus {
        outline: var(--accent-color) solid 1px;
    }

    /* Slider Design Option */

    .s--slider {
        display: flex;
        align-items: center;
    }

    .s--slider button {
        width: 3em;
        height: 1.6em;
        position: relative;
        margin: 0 0 0 0.5em;
        background: var(--gray);
        border: none;
    }

    .s--slider button::before {
        content: '';
        position: absolute;
        width: 1.3em;
        height: 1.3em;
        background: #fff;
        top: 0.13em;
        right: 1.5em;
        transition: transform 0.3s;
    }

    .s--slider button[aria-checked='true']{
        background-color: var(--accent-color)
    }

    .s--slider button[aria-checked='true']::before{
        transform: translateX(1.3em);
        transition: transform 0.3s;
    }

    .s--slider button:focus {
        box-shadow: 0 0px 0px 1px var(--accent-color);
    }

    /* Multi Design Option */

    /* Based on suggestions from Sara Soueidan https://www.sarasoueidan.com/blog/toggle-switch-design/
    and this example from Scott O'hara https://codepen.io/scottohara/pen/zLZwNv */

    .s--multi .group-container {
        border: none;
        padding: 0;
        white-space: nowrap;
    }

    label{
        cursor: url('img/link-cursor.svg'), auto;
    }

    /* .s--multi legend {
    font-size: 2px;
    opacity: 0;
    position: absolute;
    } */

    .s--multi label {
        display: inline-block;
        line-height: calc(1.6 * var(--scaleunit));
        position: relative;
        z-index: 2;
    }

    .s--multi input {
        opacity: 0;
        position: absolute;
    }

    .s--multi label:first-of-type {
        padding-right: calc(5em * var(--scaleunit));
    }

    .s--multi label:last-child {
        margin-left: calc(-5em * var(--scaleunit));
        padding-left: calc(5em * var(--scaleunit));
    }

    .s--multi:focus-within label:first-of-type:after {
        /* box-shadow: 0 0px 8px var(--accent-color); */
        border-radius: calc(1.5em * var(--scaleunit));
    }



    /* making the switch UI.  */
    .s--multi label:first-of-type:before,
    .s--multi label:first-of-type:after {
        content: "";
        height: calc(1.25em * var(--scaleunit));
        overflow: hidden;
        pointer-events: none;
        position: absolute;
        vertical-align: middle;
    }

    /* Circle */
    .s--multi label:first-of-type:before {
        border-radius: 100%;
        z-index: 2;
        position: absolute;
        width: calc(1.2em * var(--scaleunit));
        height: calc(1.2em * var(--scaleunit));
        top: calc(0.2em * var(--scaleunit));
        right: calc(1.2em * var(--scaleunit));
        transition: transform 0.3s ease;
        background: linear-gradient(to top, var(--sand100,white) 0%, var(--gray,gray) 100%);
        box-shadow: inset 0px -2px 2px 1px var(--gray,gray), inset 0px 2px 2px 1px var(--sand100,white), 0px 5px 4px -2px rgba(0,0,0,0.5);

    }

    /* PILL PRODUCT */
    .s--multi label:first-of-type:after {
        background: var(--accent-color);
        background: orange;
        box-shadow: 0.1em 0.1em 0.1em -0.05em var(--sand100,white), -0.1em -0.1em 0.1em -0.05em var(--brown,brown), inset 0px 0px 0.4em 0.5em var(--sand50,white), inset 0px 2em 2em 0px brown;
        /* border: var(--sand50) 4px solid;
        box-sizing: border-box; */
        border-radius: calc(1em * var(--scaleunit));
        margin: 0 calc(1em * var(--scaleunit));
        transition: background var(--animationquick) ease-in-out, box-shadow var(--animationquick) ease-in-out;
        width: calc(3em * var(--scaleunit));
        height: calc(1.6em * var(--scaleunit));
    }

    /* PILL LEFT */
    .s--multi input:first-of-type:checked ~ label:first-of-type:after {
        background: var(--lime100);
        box-shadow: 0.1em 0.1em 0.1em -0.05em var(--sand100,white), -0.1em -0.1em 0.1em -0.05em var(--forestgreen,darkgreen), inset 0px 0px 0.4em 0.5em var(--sand50,white), inset 0px 2em 2em 0px var(--forestgreen);


    }

    .s--multi input:first-of-type:checked ~ label:first-of-type:before {
        transform: translateX(calc(-1.4em * var(--scaleunit)));
    }

    .s--multi input:last-of-type:checked ~ label:last-of-type {
        z-index: 1;
    }

    .s--multi input:focus {
        /* box-shadow: 0 0px 8px var(--accent-color); */
        border-radius: 1.5em;
    }

    /* gravy */ 

    /* Inner Design Option */
    [role='switch'][aria-checked='true'] :first-child,
    [role='switch'][aria-checked='false'] :last-child {
        border-radius: 0.25em;
        background: var(--accent-color);
        display: inline-block;
    }

    .s--inner button:focus {
        /* box-shadow: 0 0px 8px var(--accent-color); */
        border-radius: 0.1em;
    }

    /* Slider Design Option */
    .s--slider button {
        border-radius: 1.5em;
    } 
    
    .s--slider button::before {
        border-radius: 100%;
    }

    .s--slider button:focus {
        box-shadow: 0 0px 8px var(--accent-color);
        border-radius: 1.5em;
    }
   

</style>