### Concept-2: How to pass an Anonymous function as a prop to a svelte component.

**App.svelte**

        <Slider onChange={(v) => U = v}><Slider/>

**Slider.svelte**

        export let onChange;
        export let value = 1;
        
        $: onChange(value);
        
        <input bind:value={value}>

Code Breakdown:
1. Through onChange prop, we're passing an anonymous function -

           function(v) {
               U = v;
           }

2. `v` is copied from the value attribute of the input tag by using the `bind:value={value}` (which is updated through the UI).
3. Now the global variable `U` in `App.svelte` is updated through the UI directly through the svelte component.
